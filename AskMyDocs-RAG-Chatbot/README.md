AskMyDocs — Research Paper RAG System
Overview

AskMyDocs is a Retrieval-Augmented Generation (RAG) system built to perform semantic search and grounded question answering over research papers.

The system retrieves relevant document chunks using vector search (FAISS) and generates citation-backed answers using a local Large Language Model (Ollama).

This project emphasizes evaluation-driven design, not just demo outputs.

Architecture

The system consists of four main layers:

Data Processing

Research paper metadata and abstracts

Text chunking for retrieval

Metadata preservation (doc_id, chunk_id, categories)

Vector Store

Sentence-transformer embeddings

FAISS index for similarity search

Query Pipeline

Query embedding

Top-K retrieval

Structured context building

LLM-based grounded answer generation

Citation formatting

Evaluation Layer

Precision@5

Hit@5

Category frequency analysis

Manual relevance labeling

Retrieval Workflow

User query is embedded.

FAISS retrieves top-K similar chunks.

Context is constructed with metadata.

LLM generates answer strictly from retrieved documents.

Citations reference chunk sources.

Evaluation

To measure retrieval quality, a mini benchmark of manually curated queries was created.

Metrics:

Precision@5

Hit@5

Sample Results

Average Precision@5: 0.10

Hit Rate@5: 0.50

This evaluation revealed limitations of pure embedding-based retrieval and motivated improvements such as:

Keyword re-ranking

Metadata-aware boosting

Hybrid retrieval (future work)

Key Features

Semantic retrieval using embeddings

Metadata-aware context building

Citation-grounded answer generation

Deterministic category analytics

Quantitative retrieval evaluation

Example Questions

What is preconditioned temporal difference learning?

Summarize the abstract of the top retrieved paper.

Compare the first two retrieved papers.

Which retrieved paper relates most to artificial intelligence?

Tech Stack

Python

FAISS

SentenceTransformers

Pandas

Ollama (local LLM)

Project Highlights

Built a full end-to-end RAG pipeline

Implemented structured evaluation (Precision@K)

Diagnosed retrieval weaknesses using metrics

Designed improvements based on measurable performance

This project demonstrates practical AI system design beyond basic LLM integration.