# 🚀 Financial Document Intelligence System (RAG-Based)

## 📌 Overview

This project is a **Retrieval-Augmented Generation (RAG) based Financial Document Intelligence System** built using **FastAPI, LangChain, FAISS, and Transformer embeddings**.

It enables users to:

* Upload financial documents (PDFs)
* Perform metadata-based filtering
* Execute semantic search using vector similarity
* Retrieve relevant insights from documents

---

## 🎯 Features

* 🔐 JWT Authentication (Login/Register)
* 👥 Role-Based Access Control (Admin, Analyst, Client)
* 📂 Upload Financial Documents (PDF)
* 🔍 Metadata Search (company, document type)
* 🧠 Semantic Search using FAISS + Embeddings
* ⚡ RAG Pipeline for intelligent retrieval
* 🗑️ Document Deletion (with cleanup of vector index)

---

## 🏗️ Tech Stack

* **Backend:** FastAPI
* **Database:** SQLite (SQLAlchemy ORM)
* **Authentication:** JWT (python-jose, passlib)
* **Embeddings:** Sentence Transformers (`all-MiniLM-L6-v2`)
* **Vector DB:** FAISS
* **Document Processing:** LangChain

---

## 🧠 System Architecture

```text
User → FastAPI → SQLite (Metadata)
                  ↓
             PDF Upload
                  ↓
        Text Extraction (LangChain)
                  ↓
        Chunking + Embeddings
                  ↓
             FAISS Index
                  ↓
          Semantic Search
```

---

## 🔐 Roles & Permissions

| Role    | Permissions            |
| ------- | ---------------------- |
| Admin   | Upload, Delete, Search |
| Analyst | Upload, Search         |
| Client  | Search only            |

---

## 📂 API Endpoints

### 🔹 Authentication

* `POST /auth/register` → Register new user
* `POST /auth/login` → Login and get JWT token

---

### 🔹 Document Management

* `POST /documents/upload` → Upload PDF
* `GET /documents` → Retrieve all documents
* `GET /documents/search` → Filter by metadata
* `DELETE /documents/{doc_id}` → Delete document

---

### 🔹 RAG System

* `POST /rag/index-document/{doc_id}` → Create vector index
* `GET /rag/search?query=...` → Semantic search

---

## ⚙️ Installation & Setup

### 1️⃣ Clone the repository

```bash
git clone https://github.com/your-username/financial-rag-system.git
cd financial-rag-system
```

### 2️⃣ Install dependencies

```bash
pip install fastapi uvicorn sqlalchemy python-multipart passlib[bcrypt] python-jose
pip install langchain langchain-community langchain-text-splitters
pip install sentence-transformers faiss-cpu pypdf
```

### 3️⃣ Run the application

```bash
uvicorn main:app --reload
```

### 4️⃣ Open Swagger UI

```text
http://127.0.0.1:8001/docs
```

---

## 🧪 Usage Flow

1. Register a user
2. Login and get JWT token
3. Authorize in Swagger UI
4. Upload a document
5. Index the document
6. Perform semantic search

---

## 📊 Sample Output

```json
{
  "results": [
    "The financial report shows revenue growth...",
    "Company performance improved due to..."
  ]
}
```

---

## 🚧 Challenges & Solutions

| Challenge                   | Solution                          |
| --------------------------- | --------------------------------- |
| DB inconsistency in Jupyter | Centralized session handling      |
| LangChain import errors     | Updated to latest modular imports |
| FAISS loading errors        | Enabled safe deserialization      |
| File path issues            | Added validation checks           |

---

## 🚀 Future Improvements

* 🤖 Add LLM-based answer generation (ChatGPT)
* 🌐 Build frontend UI (Streamlit / React)
* ☁️ Deploy on cloud (AWS / Render)
* 📊 Add document summarization & insights
* 🔍 Improve ranking & search accuracy

---

## 💼 Resume Highlight

> Built a RAG-based financial document intelligence system using FastAPI, FAISS, and transformer embeddings, enabling semantic search and intelligent retrieval from unstructured PDFs.

---

## 📌 Key Highlights

* End-to-end AI system
* Real-world use case
* Production-level backend
* Scalable architecture

---

## 👨‍💻 Author

**Sumeet Amin**

---
