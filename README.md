# RAG Question Answering System

## Problem
Large language models struggle to answer questions over large document collections due to context limits and hallucination. This becomes a practical issue in real-world use cases where information is spread across long PDFs.

## Solution
This project implements a Retrieval-Augmented Generation (RAG) pipeline that grounds responses in retrieved document context instead of relying solely on generation.

---

## Pipeline
1. Text → Chunking  
2. Chunk → Embeddings (SentenceTransformer)  
3. Store → FAISS vector index  
4. Query → Embedding  
5. Retrieval → Top-k similar chunks  
6. Generation → LLM produces answer  

---

## Key Focus Areas
- Improving retrieval quality through chunking strategies  
- Comparing similarity metrics (cosine vs Euclidean)  
- Experimenting with embedding models  
- Handling noisy PDF data during preprocessing  

---

## Design Decisions

### Chunking
A rolling chunking approach was used to maintain coherence across text segments. This was important for preserving semantic meaning, especially in noisy or unstructured PDF data.

### Embeddings
The model `all-MiniLM-L6-v2` (384 dimensions) was used to balance performance and computational efficiency.

### FAISS
FAISS was used for efficient similarity search and vector storage, with Euclidean distance and top-k retrieval.

### LLM
LLMs were accessed via Google Colab (Gemini) for stable and accessible inference.

---

## Modular Design
The pipeline is modular, allowing individual components (chunking, embeddings, retrieval, or generation) to be improved or replaced independently.

---

## Future Work
- Explore semantic chunking for better contextual grouping  
- Improve retrieval strategies further  
- Extend to multimodal RAG systems  

---


## Summary
This project focuses on building a practical RAG system while understanding that retrieval quality not generation is often the main bottleneck in producing reliable answers.
