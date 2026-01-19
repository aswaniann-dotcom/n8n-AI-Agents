# RAG-Powered Enterprise Knowledge Assistant

This project contains an **n8n workflow** that implements a **Retrieval-Augmented Generation (RAG)** architecture to build an enterprise-ready knowledge assistant. The workflow ingests documents from Google Drive, processes and embeds the content, stores vectors in **Pinecone**, and enables **AI-powered, context-aware question answering** over the indexed documents.

The solution is designed to support scalable document ingestion, semantic search, and conversational AI grounded in enterprise knowledge sources.

---

## 🚀 Overview

This n8n workflow automates the following:

- Ingest documents from Google Drive
- Download and process file content
- Split large documents into manageable text chunks
- Generate embeddings using OpenAI
- Store embeddings in Pinecone Vector Store
- Accept natural language questions via chat
- Retrieve relevant document context
- Generate accurate, grounded AI responses

This creates an **end-to-end RAG pipeline** for enterprise knowledge discovery and Q&A.

---

## 🔄 Workflow Execution Flow

### 1️⃣ Trigger: Manual Execution
- The workflow starts when **Execute Workflow** is clicked.
- Used to ingest and index documents into the vector store.

---

### 2️⃣ Search Files and Folders (Google Drive)
- Retrieves files from a configured Google Drive folder.
- Acts as the primary document source.

---

### 3️⃣ Download File
- Downloads each document retrieved from Google Drive.
- Passes file data for further processing.

---

### 4️⃣ Loop Over Items
- Iterates through all downloaded documents.
- Ensures scalable ingestion of multiple files.

---

### 5️⃣ Default Data Loader
- Converts document files into raw text.
- Prepares content for chunking and embedding.

---

### 6️⃣ Recursive Character Text Splitter
- Splits documents into smaller text chunks.
- Improves embedding quality and retrieval accuracy.

---

### 7️⃣ OpenAI Embeddings
- Generates semantic embeddings for each text chunk.
- Enables similarity-based retrieval.

---

### 8️⃣ Pinecone Vector Store (Ingestion)
- Stores embeddings in Pinecone.
- Provides fast and scalable vector search.

---

## 💬 Conversational Q&A Flow

### 9️⃣ Trigger: When Chat Message Received
- Activated when a user submits a question.

---

### 🔟 AI Agent
- Acts as the orchestration and reasoning layer.
- Uses:
  - Chat LLM
  - Conversation memory
  - Vector store as a knowledge source

---

### 1️⃣1️⃣ Answer Questions with Vector Store
- Retrieves relevant document chunks from Pinecone.
- Supplies retrieved context to the LLM.
- Generates grounded, context-aware responses.

---

### 1️⃣2️⃣ Respond to User
- Returns the final answer to the user.
- Ensures responses are based on enterprise documents.

---

## 🧠 Architecture Summary

<img width="518" height="222" alt="image" src="https://github.com/user-attachments/assets/7689623c-dae6-4087-8768-3ceacb00bbf8" />
<img width="384" height="300" alt="image" src="https://github.com/user-attachments/assets/4fd55d9f-5cf2-439b-83d8-56e0a2fd9169" />


---

## 🧩 Key Components

- **Google Drive Nodes** – Enterprise document ingestion
- **Recursive Text Splitter** – Chunking strategy for large files
- **OpenAI Embeddings** – Semantic representation
- **Pinecone Vector Store** – High-performance vector search
- **AI Agent** – Conversational reasoning and orchestration
- **Simple Memory** – Maintains chat context

---

## 📁 Folder Structure (Recommended)

rag-enterprise-knowledge-assistant/
├── README.md
├── rag-enterprise-knowledge-assistant.json


---

## 🔐 Required Credentials

- **Google Drive API**
  - Required for document discovery and download
- **OpenAI API**
  - Required for embeddings and chat completion
- **Pinecone API**
  - Required for vector storage and retrieval

---

## 📦 How to Use

1. Import the workflow JSON into n8n
2. Configure credentials:
   - Google Drive
   - OpenAI
   - Pinecone
3. Set the Google Drive folder containing enterprise documents
4. Click **Execute Workflow** to ingest and index documents
5. Open chat and start asking questions about the documents

---

## 💡 Use Cases

- Enterprise knowledge base
- Internal documentation assistant
- Policy and compliance Q&A
- Research and insights retrieval
- Product and technical documentation search

---

## 🔮 Future Enhancements

- Metadata-based filtering
- Role-based access control
- Multi-source ingestion (Confluence, SharePoint)
- UI integration (Slack, Web App)

---


