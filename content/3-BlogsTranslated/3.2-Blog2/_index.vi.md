---
title: "Blog 2"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---


# Trí tuệ nhân tạo: Kết hợp tìm kiếm từ khóa & ngữ nghĩa cho văn bản và hình ảnh với Amazon Bedrock và Amazon OpenSearch Service

Tác giả: Renan Bertolazzi, Birender Pal, Sarath Krishnan (24/04/2025) — Amazon Bedrock, Amazon OpenSearch Service, Amazon Titan, Intermediate (200)

Khách hàng mong muốn tìm sản phẩm nhanh, chính xác và trực quan. Trải nghiệm tìm kiếm tốt nâng chuyển đổi, AOV và giữ chân. 78% người dùng sẵn sàng mua lại nếu được cá nhân hóa. Với danh mục lớn, hybrid search là lợi thế chiến lược.

- **Keyword search**: khớp chính xác tên/thuộc tính.  
- **Semantic search**: dùng embeddings để hiểu ngữ nghĩa, chịu biến thể diễn đạt, hỗ trợ đa phương thức (văn bản + hình ảnh).  
- **Hybrid search**: kết hợp điểm keyword + semantic; thường cải thiện chất lượng 8–12% so với keyword và ~15% so với natural language.

Amazon OpenSearch Service là vector database được khuyến nghị cho Amazon Bedrock, cung cấp tìm kiếm vector độ trễ mili-giây. Amazon Titan Multimodal Embeddings G1 (qua Bedrock) tạo embedding chung cho văn bản và hình ảnh, cho phép truy vấn liên phương thức.

Mục tiêu: Xây dựng giải pháp hybrid search đa phương thức, cho phép người dùng gửi văn bản và/hoặc ảnh để truy xuất kết quả liên quan từ bộ dữ liệu hình ảnh bán lẻ mẫu.

---

## Tổng quan kiến trúc

Hai luồng chính:

- **Ingestion**: sinh multimodal embeddings (văn bản, ảnh, metadata) bằng Bedrock (Titan) và lưu vào OpenSearch.  
- **Query**: search pipeline trên OpenSearch kết hợp keyword + neural search; normalization processor chuẩn hóa và gộp điểm.

Thành phần:
- Amazon Bedrock (Titan Multimodal Embeddings G1)  
- Amazon OpenSearch Service (vector + hybrid pipeline)  
- Amazon S3 (lưu dữ liệu nguồn)  
- Amazon SageMaker Notebook (ingestion, kiểm thử)  
- (Tùy chọn) SNS/SQS/Step Functions cho orchestration

---

## Quy trình nhập dữ liệu (Data ingestion)

1) Đọc văn bản, ảnh, metadata từ S3; mã hóa ảnh Base64.  
2) Gửi dữ liệu tới Bedrock (Titan) để tạo embeddings.  
3) Lưu embeddings + metadata vào OpenSearch (bulk).  

Ví dụ tạo index (rút gọn):
```yaml
settings:
  index.knn: true
  number_of_shards: 2
mappings:
  properties:
    amazon_titan_multimodal_embeddings:
      type: knn_vector
      dimension: 1024
      method:
        name: hnsw
        engine: lucene
```

---

## Quy trình truy vấn (Query workflow)

1) Client gửi truy vấn: văn bản, ảnh Base64, hoặc cả hai.  
2) Pipeline chạy:
   - Keyword search (multi_match).  
   - Neural search (embedding từ Titan cho văn bản/ảnh).  
3) Normalization (ví dụ `min_max`) + combination (`arithmetic_mean`) gộp điểm.  
4) Trả về kết quả xếp hạng cuối.

Ví dụ search pipeline:
```json
{
  "phase_results_processors": [
    {
      "normalization-processor": {
        "normalization": { "technique": "min_max" },
        "combination": {
          "technique": "arithmetic_mean",
          "parameters": {
            "weights": [OPENSEARCH_KEYWORD_WEIGHT, 1 - OPENSEARCH_KEYWORD_WEIGHT]
          }
        }
      }
    }
  ]
}
```

Ví dụ truy vấn hybrid:
```json
{
  "query": {
    "hybrid": {
      "queries": [
        { "multi_match": { "query": "<query_text>" } },
        {
          "neural": {
            "vector_embedding": {
              "query_text": "<query_text>",
              "query_image": "<base64_image>",
              "model_id": "<titan_connector_model_id>",
              "k": 5
            }
          }
        }
      ]
    }
  }
}
```

---

## Điều kiện tiên quyết

- Tài khoản AWS.  
- Bedrock bật Amazon Titan Multimodal Embeddings G1.  
- OpenSearch Service domain.  
- SageMaker notebook.  
- Kiến thức IAM, EC2, OpenSearch, SageMaker, Python.  
- Mã nguồn mẫu trên GitHub.

---

## Tạo connector Amazon Bedrock trong OpenSearch Service

- IAM role cho phép `bedrock:InvokeModel` với Titan Multimodal Embeddings G1; trust `opensearchservice.amazonaws.com`.
- Đăng ký model group, tạo connector, triển khai model trong OpenSearch (deploy=true).

---

## Tạo search pipeline & bật hybrid search

- Dùng normalization (min_max) + combination (arithmetic_mean) để gộp điểm keyword/semantic.  
- Điều chỉnh trọng số `OPENSEARCH_KEYWORD_WEIGHT` theo nhu cầu.

---

## Nhập dữ liệu mẫu

- Chọn thuộc tính tạo embeddings; chuyển ảnh Base64; sinh embedding Titan; bulk vào index.  
- Dataset mẫu: sản phẩm bán lẻ (hình ảnh + metadata).

---

## Tạo hàm truy vấn kiểm thử

- **Keyword search**: `multi_match` với `query_text`.  
- **Semantic search**: `neural` với `query_text`, `query_image`, `model_id`.  
- **Hybrid search**: kết hợp hai truy vấn trên qua pipeline.

---

## Thử nghiệm

- Keyword: bám tên/thuộc tính, thiếu ngữ cảnh.  
- Semantic: hiểu ngữ cảnh, đôi khi ưu tiên hình ảnh hơn màu sắc.  
- Hybrid: gộp điểm, đẩy kết quả phù hợp (đúng màu + phong cách) lên đầu.

---

## Dọn dẹp

Xóa index, model deployment, model, model group, connector Bedrock; nếu tạo domain riêng cho lab, có thể xóa domain hoặc chỉ xóa tài nguyên thử nghiệm để tránh chi phí.

---

## Kết luận

Hybrid search đa phương thức trên OpenSearch Service kết hợp điểm mạnh keyword + semantic, nhờ Titan Multimodal Embeddings G1 (Bedrock). Hỗ trợ truy vấn văn bản + hình ảnh, cho kết quả chính xác và phù hợp hơn. Thử notebook, tinh chỉnh normalization/trọng số. Nếu cần model tùy chỉnh trên SageMaker, xem “Hybrid Search with Amazon OpenSearch Service”; nếu chỉ cần semantic, tham khảo hướng dẫn search text & image với Bedrock + OpenSearch.

---

## Về tác giả

- **Renan Bertolazzi** – Kiến trúc sư Giải pháp Doanh nghiệp tại AWS, hỗ trợ khách hàng đổi mới và đơn giản hóa.  
- **Birender Pal** – Kiến trúc sư Giải pháp Cấp cao tại AWS, tập trung cloud-native, ML, GenAI.  
- **Sarath Krishnan** – Kiến trúc sư Giải pháp Cấp cao tại AWS, kinh nghiệm high availability, tối ưu chi phí; trọng tâm DevOps, ML, MLOps, AI tạo sinh.