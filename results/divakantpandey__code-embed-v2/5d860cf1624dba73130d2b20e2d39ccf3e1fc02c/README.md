---
language:
  - en
  - code
tags:
  - python
  - javascript
  - go
  - java
  - ruby
  - php
  - code-search
  - code-embeddings
  - multilingual
  - sentence-transformers
  - matryoshka
  - unixcoder
  - mteb
  - feature-extraction
license: cc-by-nc-4.0
pipeline_tag: feature-extraction
library_name: sentence-transformers
metrics:
  - mrr
  - ndcg
  - map
model-index:
  - name: code-embed-v2
    results:
      - task:
          type: retrieval
          name: MTEB(Code, v1)
        dataset:
          name: MTEB(Code, v1) Macro-Average
          type: mteb/code
        metrics:
          - type: ndcg_at_10
            value: 0.4064
            name: NDCG@10 (meanTask)
          - type: mrr_at_10
            value: 0.3781
            name: MRR@10 (meanTask)
      - task:
          type: retrieval
          name: CoIR
        dataset:
          name: CoIR Benchmark Macro-Average
          type: coir
        metrics:
          - type: ndcg_at_10
            value: 0.3729
            name: NDCG@10 (meanTask)
          - type: mrr_at_10
            value: 0.3478
            name: MRR@10 (meanTask)
      - task:
          type: retrieval
          name: CoREB(v1)
        dataset:
          name: CoREB(v1) Macro-Average
          type: coreb
        metrics:
          - type: ndcg_at_10
            value: 0.2711
            name: NDCG@10 (meanTask)
      - task:
          type: retrieval
          name: Code Search
        dataset:
          name: CodeSearchNetRetrieval
          type: code_search_net
          split: test
        metrics:
          - type: ndcg_at_10
            value: 0.7778
            name: NDCG@10 (Multilingual)
          - type: mrr_at_10
            value: 0.7385
            name: MRR@10 (Multilingual)
      - task:
          type: retrieval
          name: COIR Code Search
        dataset:
          name: COIRCodeSearchNetRetrieval
          type: coir_code_search_net
          split: test
        metrics:
          - type: ndcg_at_10
            value: 0.7443
            name: NDCG@10 (Multilingual)
          - type: mrr_at_10
            value: 0.7137
            name: MRR@10 (Multilingual)
      - task:
          type: retrieval
          name: StackOverflow QA
        dataset:
          name: StackOverflowQA
          type: stackoverflow_qa
          split: test
        metrics:
          - type: ndcg_at_10
            value: 0.5530
            name: NDCG@10
          - type: mrr_at_10
            value: 0.5159
            name: MRR@10
      - task:
          type: retrieval
          name: Code Feedback (Single-Turn)
        dataset:
          name: CodeFeedbackST
          type: code_feedback_st
          split: test
        metrics:
          - type: ndcg_at_10
            value: 0.4693
            name: NDCG@10
          - type: mrr_at_10
            value: 0.4251
            name: MRR@10
      - task:
          type: retrieval
          name: Code-to-Code Search
        dataset:
          name: CodeSearchNetCCRetrieval
          type: code_search_net_cc
          split: test
        metrics:
          - type: ndcg_at_10
            value: 0.4170
            name: NDCG@10
          - type: mrr_at_10
            value: 0.3784
            name: MRR@10
      - task:
          type: retrieval
          name: Code Edit Search
        dataset:
          name: CodeEditSearchRetrieval
          type: code_edit_search
          split: train
        metrics:
          - type: ndcg_at_10
            value: 0.3703
            name: NDCG@10
          - type: mrr_at_10
            value: 0.3283
            name: MRR@10
      - task:
          type: retrieval
          name: Cross-Language Translation
        dataset:
          name: CodeTransOceanContest
          type: code_trans_ocean_contest
          split: test
        metrics:
          - type: ndcg_at_10
            value: 0.3640
            name: NDCG@10
          - type: mrr_at_10
            value: 0.3150
            name: MRR@10
      - task:
          type: retrieval
          name: Framework Translation
        dataset:
          name: CodeTransOceanDL
          type: code_trans_ocean_dl
          split: test
        metrics:
          - type: ndcg_at_10
            value: 0.3439
            name: NDCG@10
          - type: mrr_at_10
            value: 0.2204
            name: MRR@10
      - task:
          type: retrieval
          name: Text to SQL
        dataset:
          name: SyntheticText2SQL
          type: synthetic_text2sql
          split: test
        metrics:
          - type: ndcg_at_10
            value: 0.3277
            name: NDCG@10
          - type: mrr_at_10
            value: 0.2513
            name: MRR@10
      - task:
          type: retrieval
          name: Code Feedback (Multi-Turn)
        dataset:
          name: CodeFeedbackMT
          type: code_feedback_mt
          split: test
        metrics:
          - type: ndcg_at_10
            value: 0.3188
            name: NDCG@10
          - type: mrr_at_10
            value: 0.2882
            name: MRR@10
      - task:
          type: retrieval
          name: Web Query Code Search
        dataset:
          name: CosQA
          type: cosqa
          split: test
        metrics:
          - type: ndcg_at_10
            value: 0.1599
            name: NDCG@10
          - type: mrr_at_10
            value: 0.1135
            name: MRR@10
      - task:
          type: retrieval
          name: Algorithmic Problem Retrieval
        dataset:
          name: AppsRetrieval
          type: apps_retrieval
          split: test
        metrics:
          - type: ndcg_at_10
            value: 0.0306
            name: NDCG@10
          - type: mrr_at_10
            value: 0.0241
            name: MRR@10
---

# 💻 code-embed-v2

**CodeEmbed v2** is a lightweight, state-of-the-art multilingual code embedding model (≤131M parameters) developed by **[Divakant Pandey](https://github.com/divakantpandey)**. Specialized for semantic code search, code-to-code retrieval, text-to-SQL mapping, and repository navigation across **6 major programming languages** with an extended **8,192 token context window** and native **Matryoshka Representation Learning (MRL)**.

---

## 🚀 Highlights & Functional Capabilities

- **Multilingual Support**: High-accuracy semantic search across **Python, JavaScript, Go, Java, Ruby, and PHP**.
- **Extended Context**: Full **8,192 token context window** allowing whole-file, multi-function, and long class embeddings without aggressive truncation.
- **Matryoshka Representation Learning (MRL)**: Embeddings can be dynamically truncated from **1536** down to **768, 384, 256, 128, or 64 dimensions** with negligible loss in accuracy, enabling significant vector database memory and latency savings.
- **Compact & Efficient**: ~131M parameters (**~484 MB** safetensors footprint) optimized for low-latency CPU inference and fast GPU batch indexing.
- **Universal Compatibility**: Works out of the box with `sentence-transformers`, `transformers`, and PyTorch.

---

## 📊 Benchmark Performance

CodeEmbed v2 was thoroughly evaluated across **18 official benchmark tasks** comprising the primary code retrieval suites on the Massive Text Embedding Benchmark (MTEB):

### 🏆 Benchmark Suite Macro-Averages (`meanTask`)

| Benchmark Suite | Total Tasks | Metric | Official Macro-Average | Coverage |
| :--- | :---: | :---: | :---: | :---: |
| **`MTEB(Code, v1)`** | **12 / 12** | **NDCG@10** | **`40.64%`** | **100% (Complete)** |
| **`CoIR` (Code IR)** | **10 / 10** | **NDCG@10** | **`37.29%`** | **100% (Complete)** |
| **`CoREB(v1)`** | **6 / 6** | **NDCG@10** | **`27.11%`** | **100% (Complete)** |

### 📋 Detailed Task-by-Task Scorecard

| Task | Category | NDCG@10 | MRR@10 | Evaluation Scope |
| :--- | :--- | :---: | :---: | :--- |
| **`CodeSearchNetRetrieval`** | Text-to-Code Search | **77.78%** | 73.85% | 6 Languages (Python, JS, Go, Java, Ruby, PHP) |
| **`COIRCodeSearchNetRetrieval`** | Multilingual Search | **74.43%** | 71.37% | Full-scale 300k+ codebase corpus |
| **`CorebC2TReranking`** | Code-to-Text Reranking | **66.74%** | 57.59% | Cross-lingual code description ranking |
| **`StackOverflowQA`** | Developer Q&A Search | **55.30%** | 51.59% | Real-world developer query matching |
| **`CodeFeedbackST`** | Instruction Feedback | **46.93%** | 42.51% | Single-turn instruction and code feedback |
| **`CodeSearchNetCCRetrieval`** | Code-to-Code Search | **41.70%** | 37.84% | Cross-language code function matching |
| **`CodeEditSearchRetrieval`** | Edit / Patch Search | **37.03%** | 32.83% | 13 Git commit and patch subsets |
| **`CorebC2CReranking`** | Code-to-Code Reranking | **36.87%** | 34.40% | Direct code snippet similarity ranking |
| **`CodeTransOceanContest`** | Code Translation | **36.40%** | 31.50% | Cross-language algorithmic translation |
| **`CodeTransOceanDL`** | Framework Translation | **34.39%** | 22.04% | Deep learning API cross-matching |
| **`SyntheticText2SQL`** | Text-to-SQL | **32.77%** | 25.13% | Natural language to structured SQL queries |
| **`CodeFeedbackMT`** | Multi-Turn Feedback | **31.88%** | 28.82% | Conversational multi-turn code context |
| **`CorebT2CReranking`** | Text-to-Code Reranking | **26.44%** | 27.65% | Natural language to code reranking |
| **`CorebC2TRetrieval`** | Code-to-Text Search | **22.32%** | 18.83% | Source code to documentation retrieval |
| **`CosQA`** | Web Query Code Search | **15.99%** | 11.35% | Real-world noisy web search queries |
| **`CorebT2CRetrieval`** | Text-to-Code Search | **7.45%** | 8.10% | Zero-shot query to code retrieval |
| **`AppsRetrieval`** | Algorithmic Problem Search | **3.06%** | 2.41% | Hard algorithmic programming specifications |
| **`CorebC2CRetrieval`** | Code-to-Code Retrieval | **2.87%** | 2.25% | Direct code-to-code corpus retrieval |

---

## 💻 Quickstart Usage

### 1. Basic Semantic Code Search with `sentence-transformers`

```python
from sentence_transformers import SentenceTransformer

# Load model directly from Hugging Face Hub
model = SentenceTransformer("divakantpandey/code-embed-v2")

queries = [
    "binary search implementation",
    "fetch json from api endpoint",
    "goroutine channel worker pool"
]

code_snippets = [
    "def binary_search(arr, target):\n    left, right = 0, len(arr) - 1\n    while left <= right:\n        mid = (left + right) // 2\n        if arr[mid] == target: return mid\n        elif arr[mid] < target: left = mid + 1\n        else: right = mid - 1\n    return -1",
    "async function fetchJSON(url) {\n    const response = await fetch(url);\n    return await response.json();\n}",
    "func worker(id int, jobs <-chan int, results chan<- int) {\n    for j := range jobs {\n        results <- j * 2\n    }\n}"
]

# Generate normalized embeddings
query_embeddings = model.encode(queries, normalize_embeddings=True)
code_embeddings = model.encode(code_snippets, normalize_embeddings=True)

# Compute cosine similarity
similarity_matrix = query_embeddings @ code_embeddings.T
print(similarity_matrix)
```

### 2. Matryoshka Dimension Truncation (Adaptive Dimensions)

CodeEmbed v2 natively supports Matryoshka Representation Learning. You can truncate embeddings to smaller dimensions (e.g., 768, 384, 256) for faster vector database indexing with minimal accuracy impact:

```python
# Truncate to 768 dimensions (50% storage & compute reduction)
compact_query_embs = model.encode(queries, truncate_dim=768, normalize_embeddings=True)
compact_code_embs = model.encode(code_snippets, truncate_dim=768, normalize_embeddings=True)

similarity = compact_query_embs @ compact_code_embs.T
```

---

## 📜 License & Commercial Terms

This model and its associated weights are licensed under the **Creative Commons Attribution-NonCommercial 4.0 International Public License (CC-BY-NC 4.0)**.

- **Non-Commercial Use:** Free for academic research, educational use, personal exploration, open-source evaluations, and non-commercial benchmarking with appropriate attribution.
- **Attribution:** Please attribute **Divakant Pandey** and reference the repository at [https://github.com/divakantpandey/code-embed](https://github.com/divakantpandey/code-embed).
- **Commercial Licensing:** To license CodeEmbed v2 for commercial products, enterprise SaaS applications, closed-source systems, or proprietary developer tools, please contact:
  - **Licensor / Maintainer:** Divakant Pandey
  - **Email:** `divakant01@gmail.com`
  - **GitHub:** [@divakantpandey](https://github.com/divakantpandey)
