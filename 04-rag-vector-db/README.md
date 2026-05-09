# 🔍 RAG & Vector Database Workflows

Retrieval-Augmented Generation (RAG) systems that connect AI models to persistent knowledge bases using vector databases. These workflows allow AI agents to answer questions grounded in real documents and data.

---

## Workflows

### 1. Agentic RAG System
**Stack:** Chat Trigger → OpenAI Agent → MCP Client Tool (Vector Retrieval)  
A fully agentic RAG system where the AI decides when and what to retrieve from the vector store. Uses MCP to expose the retrieval tool to the agent, enabling dynamic, query-driven knowledge lookup.

### 2. Supabase RAG Agent
**Stack:** Chat Trigger → Agent → Supabase pgvector → OpenAI Embeddings  
Uses Supabase's built-in pgvector extension as the vector store. Embeds documents with OpenAI, stores them in Supabase, and retrieves semantically similar chunks at query time.

### 3. RAG Document System
**Stack:** Document Ingestion → Chunking → Embedding → Vector Store → Query Pipeline  
A complete RAG pipeline: ingests documents, chunks and embeds them, stores vectors, and serves a retrieval endpoint. Modular design makes it easy to swap out the vector DB or embedding model.

### 4. Vector DB Integration
**Stack:** HTTP Webhooks → Embedding Model → Vector DB Write/Read  
A standalone integration layer that exposes vector database operations (upsert, query, delete) via webhooks. Can be used as a reusable tool by other agent workflows.

---

## Key Concepts Demonstrated
- End-to-end RAG pipeline design (ingest → embed → retrieve → generate)
- Supabase pgvector as a production vector store
- MCP-based tool exposure for agentic retrieval
- Document chunking and embedding strategies
- Modular, reusable vector DB integration patterns
