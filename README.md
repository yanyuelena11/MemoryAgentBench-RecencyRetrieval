# MemoryAgentBench-RecencyRetrieval
Embedding-RAG reproduction and recency-aware retrieval project

## Upstream Repository

This project builds on MemoryAgentBench:

https://github.com/HUST-AI-HYZ/MemoryAgentBench

The original repository provides the benchmark dataset, evaluation
framework, and embedding-RAG implementation.

## Modifications

This reproduction makes the following changes:

- Uses Contriever as the local embedding model.
- Uses DeepSeek Flash instead of GPT-4o-mini for answer generation.
- Uses DeepSeek through its OpenAI-compatible API.
- Disables DeepSeek thinking mode for the benchmark’s 10-token output limit.
- Evaluates FactConsolidation-SH 32K using 512-token chunks and top-10 retrieval.
- Adds compatibility adjustments for the current LangChain version.

## Experimental Setup

- Dataset: FactConsolidation-SH 32K
- Questions: 100
- Chunk size: 512 tokens
- Retriever: Contriever
- Vector index: FAISS
- Retrieved chunks: Top 10
- Generator: DeepSeek Flash
- Temperature: 0.0
- Thinking mode: Disabled

## Results

- Exact match: 27.00%
- F1: 28.57%
- Substring exact match: 28.00%
- ROUGE-L F1: 28.57%
- Average query time: 1.17 seconds
