# RAG-Based QA AI Agent

An AI-powered document Q&A agent built with n8n, using Retrieval-Augmented Generation (RAG) to answer questions from uploaded documents with conversational memory.

## 📋 Overview

This project lets you upload any document and ask natural language questions about its content. It uses embeddings and vector search to retrieve relevant context, then generates accurate answers using Google Gemini — with support for follow-up questions through conversation memory.

## 🛠️ Tech Stack

- **n8n** — workflow automation and orchestration
- **Google Gemini API** — answer generation
- **Hugging Face API** — embedding generation (`BAAI/bge-small-en-v1.5`)
- **Pinecone** — vector database for storing and retrieving embeddings

## ⚙️ Setup

### 1. Prerequisites

- Node.js installed (for running n8n locally)
- API keys for Google Gemini, Hugging Face, and Pinecone

### 2. Start n8n

For local installation:

```bash
npx n8n
```

Or use an existing n8n Cloud instance.

### 3. Configure Credentials

Add the following credentials in n8n:

- Google Gemini API
- Hugging Face API
- Pinecone API

### 4. Create Pinecone Index

Create a Dense Pinecone index with:

- **Dimension:** 384
- **Metric:** cosine

The dimension must match the embedding model:

```
BAAI/bge-small-en-v1.5
```

### 5. Import the n8n Workflow

Import the workflow JSON file from:

```
n8n/rag-workflow.json
```

Connect your API credentials to the required nodes.

### 6. Run the Workflow

Activate the workflow and open the n8n form/chat interface.

## 🚀 Usage

### Upload a Document

Upload your document through the n8n form.

The workflow processes the document by extracting the text, creating chunks, generating embeddings, and storing them in Pinecone.

### Ask Questions

After uploading the document, ask a question related to its content.

Example:

```
What is the main purpose of this document?
```

The AI Agent retrieves relevant information from Pinecone and generates an answer using Gemini.

### Follow-up Questions

Conversation memory allows users to ask follow-up questions.

Example:

```
User: What is the main purpose of this document?
AI: The main purpose is ...

User: Can you explain it in simple terms?
AI: Sure, ...
```

## 📸 Screenshots
<img width="1319" height="485" alt="2026-08-16" src="https://github.com/user-attachments/assets/d02030df-d658-4ae2-ab58-e996a1af5d33" />

- n8n Workflow
- Document Upload
- AI Q&A

## 📁 Project Structure

```
RAG-Based-QA-AI-Agent/

├── README.md

```

## 🔮 Future Improvements

- [ ] Support multiple document formats
- [ ] Add metadata-based filtering
- [ ] Add reranking for better retrieval
- [ ] Add source citations to responses
- [ ] Add authentication and user-specific knowledge bases
- [ ] Add retrieval and answer-quality evaluation
- [ ] Support multi-document querying


## 👨‍💻 Author
Abhishek Rauniyar
