---
title: "Blog 2"
date: "2025-09-09T19:53:52+07:00"
weight: 1
chapter: false
pre: " <b> 3.2. </b> "
---


# AI: Combine keyword & semantic search for text and images with Amazon Bedrock and Amazon OpenSearch Service

Authors: Renan Bertolazzi, Birender Pal, Sarath Krishnan (24/04/2025) — Amazon Bedrock, Amazon OpenSearch Service, Amazon Titan, Intermediate (200)

Shoppers want fast, accurate, and intuitive search. Great search improves conversion, AOV, and retention; 78% of users will buy again if experiences are personalized. With large catalogs, hybrid search is a strategic advantage.

- **Keyword search**: exact match on names/attributes.  
- **Semantic search**: embeddings to capture meaning, resilient to phrasing, supports multimodal (text + image).  
- **Hybrid search**: blends keyword + semantic scores; often improves quality 8–12% vs keyword and ~15% vs natural language (per OpenSearch).

Amazon OpenSearch Service is the recommended vector database for Amazon Bedrock, delivering millisecond-latency vector search at scale. Amazon Titan Multimodal Embeddings G1 (via Bedrock) creates a shared embedding space for text and images, enabling cross-modal queries.

Goal: Build a multimodal hybrid search solution that lets users submit text and/or images to retrieve relevant results from a sample retail image dataset.

---

## Architecture overview

Two main flows:

- **Ingestion**: generate multimodal embeddings (text, image, metadata) with Bedrock (Titan) and store in OpenSearch.  
- **Query**: OpenSearch search pipeline combines keyword + neural search; normalization processor standardizes and blends scores.

Components:
- Amazon Bedrock (Titan Multimodal Embeddings G1)  
- Amazon OpenSearch Service (vector + hybrid pipeline)  
- Amazon S3 (source data)  
- Amazon SageMaker Notebook (ingestion, testing)  
- (Optional) SNS/SQS/Step Functions for orchestration

---

## Data ingestion

1) Read text, images, metadata from S3; Base64-encode images.  
2) Send data to Bedrock (Titan) to get embeddings.  
3) Store embeddings + metadata into OpenSearch (bulk).  

Example index (shortened):
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

## Query workflow

1) Client sends text, Base64 image, or both.  
2) Pipeline runs:
   - Keyword search (multi_match).  
   - Neural search (Titan embeddings for text/image).  
3) Normalization (e.g., `min_max`) + combination (`arithmetic_mean`) to blend scores.  
4) Return ranked results.

Example search pipeline:
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

Hybrid query example:
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

## Prerequisites

- AWS account.  
- Bedrock with Amazon Titan Multimodal Embeddings G1 enabled.  
- OpenSearch Service domain.  
- SageMaker notebook.  
- Familiarity with IAM, EC2, OpenSearch, SageMaker, Python.  
- Sample code on GitHub.

---

## Create the Amazon Bedrock connector in OpenSearch Service

- IAM role allowing `bedrock:InvokeModel` for Titan Multimodal Embeddings G1; trust `opensearchservice.amazonaws.com`.  
- Register model group, create connector, deploy model in OpenSearch (`deploy=true`).

---

## Build the search pipeline & enable hybrid search

- Use normalization (min_max) + combination (arithmetic_mean) to merge keyword/semantic scores.  
- Tune `OPENSEARCH_KEYWORD_WEIGHT` as needed.

---

## Ingest sample data

- Select fields for embeddings; Base64 images; generate Titan embeddings; bulk into the index.  
- Sample dataset: retail products (images + metadata).

---

## Create query functions for testing

- **Keyword search**: `multi_match` with `query_text`.  
- **Semantic search**: `neural` with `query_text`, `query_image`, `model_id`.  
- **Hybrid search**: combine both via the pipeline.

---

## Test observations

- Keyword: exact on names/attributes, misses context.  
- Semantic: understands context, may overweight image vs. color.  
- Hybrid: blended scoring surfaces the most relevant (right color + style).

---

## Cleanup

Delete index, model deployment, model, model group, Bedrock connector; if you created a dedicated domain for the lab, delete it or remove test resources to avoid costs.

---

## Conclusion

Multimodal hybrid search on OpenSearch Service combines keyword + semantic strengths using Titan Multimodal Embeddings G1 (Bedrock). It supports text + image queries for more accurate, relevant results. Try the notebook, tune normalization/weights. For custom models on SageMaker, see “Hybrid Search with Amazon OpenSearch Service”; for semantic-only, see Bedrock + OpenSearch guides for text and image search.

---

## About the authors

- **Renan Bertolazzi** – Enterprise Solutions Architect at AWS, helps customers innovate and simplify.  
- **Birender Pal** – Senior Solutions Architect at AWS, focused on cloud-native, ML, GenAI.  
- **Sarath Krishnan** – Senior Solutions Architect at AWS, experienced in high availability and cost optimization; focuses on DevOps, ML, MLOps, generative AI.