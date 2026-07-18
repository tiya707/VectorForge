# VectorForge

A high-performance local Vector Database and Retrieval-Augmented Generation (RAG) application built in C++. VectorForge combines multiple vector search algorithms with local LLM inference using Ollama to provide fast semantic search and document-based question answering through an interactive web interface.

---

## Features

- Semantic vector search
- Multiple search algorithms
  - HNSW
  - KD-Tree
  - Brute Force
- Multiple distance metrics
  - Cosine Similarity
  - Euclidean Distance
  - Manhattan Distance
- Document embedding using Ollama
- Retrieval-Augmented Generation (RAG)
- Interactive web dashboard
- Search latency comparison
- REST API for search and document management

---

## Tech Stack

### Backend
- C++17
- cpp-httplib

### AI
- Ollama
- llama3.2
- nomic-embed-text

### Frontend
- HTML
- CSS
- JavaScript

---

## Project Structure

```
VectorForge/
│
├── main.cpp
├── httplib.h
├── index.html
├── README.md
└── .gitignore
```

---

## Getting Started

### Prerequisites

Install the following:

- Git
- Ollama
- C++17 Compiler (GCC/Clang)

### Install Ollama Models

```bash
ollama pull nomic-embed-text
ollama pull llama3.2
```

### Clone Repository

```bash
git clone https://github.com/tiya707/Vector-Forge.git
cd Vector-Forge
```

### Compile

macOS / Linux

```bash
g++ -std=c++17 -O2 main.cpp -o db
```

Windows

```bash
g++ -std=c++17 -O2 main.cpp -o db -lws2_32
```

### Run

Start Ollama if it is not already running.

```bash
ollama serve
```

Run the server.

```bash
./db
```

Open your browser:

```
http://localhost:8080
```

---

## Application Overview

### Search

- Perform semantic vector search
- Compare HNSW, KD-Tree and Brute Force
- Choose different distance metrics
- View search latency

### Documents

- Insert text documents
- Generate embeddings using Ollama
- Store document vectors

### Ask AI

- Ask questions about uploaded documents
- Retrieve relevant context
- Generate responses locally using llama3.2

---

## Architecture

```
User Query
      │
      ▼
Embedding Model
(nomic-embed-text)
      │
      ▼
Vector Database
(HNSW / KD-Tree / Brute Force)
      │
      ▼
Top Relevant Results
      │
      ▼
LLM
(llama3.2)
      │
      ▼
Generated Response
```

---

## REST Endpoints

| Method | Endpoint | Description |
|---------|----------|-------------|
| GET | `/search` | Vector search |
| POST | `/insert` | Insert vector |
| DELETE | `/delete/:id` | Delete vector |
| GET | `/items` | List vectors |
| POST | `/doc/insert` | Insert document |
| POST | `/doc/ask` | Ask AI |
| GET | `/status` | Ollama status |

---

## Future Improvements

- PDF upload support
- Persistent vector storage
- Larger datasets
- Streaming LLM responses
- User authentication
- Dark mode
- Performance analytics

---

## License

This project is licensed under the MIT License.