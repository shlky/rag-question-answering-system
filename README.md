# RAG
## Overview 
This is a Retrival-Augmented Generation(RAG) system MVP, that can easily be used any-size PDF document for personal or enterprise level.

## Pipeline
1. Text → Chunking  
2. Chunk → Embeddings (SentenceTransformer)  
3. Store → FAISS vector index  
4. Query → Embedding  
5. Retrieval → Top-k similar chunks  
6. Generation → LLM produces answer

## Design Decision

### Chunking
A Rolling Chunk is used to maintain coherence in the sementic meaning of the chunks. However Sementic Chunking can be used to preserve better meaning.

### Embeddings
The model all-MiniLM-L6-v2 was used with vector dimensions 384. This is done keeping in mind a faster compute.

### FAISS 
For Similarity Search and Vector Database. Eucleadian distance similarity with top-k retrieved

### LLMs 
LLMs used were google colab AI as it is reliable and stable 

## Modular design
Each part of the pipeline is modular and thus Quality Imporvement can easily be sought from any part of the pipeline. EX-different embedding method or different LLMs.





 
