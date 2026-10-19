# Hybrid Retrieval Engine
A collection of information retrieval experiments, starting with inverted indexes, TF-IDF ranking, and posting-list compression. The project will later be extended to dense retrieval and hybrid search.

## Implemented Features

- **Inverted Index:** Build an inverted index from tokenized documents.
- **Boolean Retrieval:** Perform AND queries using two-pointer posting-list intersection.
- **TF-IDF Ranking:** Rank documents using TF-IDF weights and cosine similarity.
- **Index Compression:** Apply d-gap encoding and Variable Byte encoding to posting lists, with decoding tests.
- **Compression Experiments:** Measure posting-list storage and encoding/decoding time using the 20 Newsgroups dataset.

## Files

| File | Description |
| --- | --- |
| `01_build_inverted_index.ipynb` | Basic retrieval algorithms and compression examples using seven sample documents. |
| `02_compression_experiment.ipynb` | Compression experiments using 1,000 documents from 20 Newsgroups. |
| `requirements.txt` | Required Python packages. |

## Getting Started

Install the dependencies:

```bash
pip install -r requirements.txt
```

Launch Jupyter Notebook:

```bash
jupyter notebook
```

Run the notebooks from top to bottom. The first notebook uses sample documents defined in the code. The second uses `fetch_20newsgroups` from scikit-learn, which downloads the dataset if it is not already cached.

## Compression Results

The saved experiment results from 1,000 documents are:

| Metric | Result |
| --- | ---: |
| Unique terms | 19,216 |
| Uncompressed posting IDs | 377,332 bytes |
| Compressed posting IDs | 118,851 bytes |
| Storage reduction | **68.5%** |

The uncompressed baseline assumes 4 bytes per document ID. The compressed size counts bytes produced by d-gap and Variable Byte encoding. These results measure posting-ID storage only, not total index memory usage.

## Next Steps

- Implement a basic dense retrieval pipeline using text embeddings.
- Combine sparse and dense retrieval into a hybrid search prototype.
- Evaluate retrieval quality, query latency, and index storage.
- Explore succinct data structures and rank/select operations for efficient indexing.

This repository is a work in progress. Dense retrieval and hybrid search are planned but not yet implemented.
