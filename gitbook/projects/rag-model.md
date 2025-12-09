# RAG Model

A complete Retrieval-Augmented Generation (RAG) system implementation with vector database, embeddings, and intelligent document retrieval.

## Overview

The RAG Model project implements a full RAG pipeline that:

* Ingests and processes documents (TXT, MD, JSON)
* Creates embeddings using transformer models
* Stores embeddings in a vector database (FAISS)
* Retrieves relevant documents for queries
* Generates answers using retrieved context

## Features

* ✅ **Document Processing**: Supports multiple file formats
* ✅ **Vector Database**: FAISS for efficient similarity search
* ✅ **Embeddings**: Sentence transformers for high-quality embeddings
* ✅ **Retrieval**: Semantic search with configurable top-k
* ✅ **Generation**: Integration with Ollama for local LLM inference
* ✅ **Interactive CLI**: Command-line interface for querying

## Installation

```bash
cd projects/RAG_Model
pip install -r requirements.txt
```

**Key Dependencies:**

* langchain
* faiss-cpu (or faiss-gpu)
* sentence-transformers
* numpy
* torch

## Quick Start

### Basic Usage

```bash
python main.py
```

The system will:

{% stepper %}
{% step %}
### Create sample documents (if none exist)

The project will generate sample documents for you to get started.
{% endstep %}

{% step %}
### Build or load the vector store

Embeddings will be created and stored in the FAISS vector store, or an existing store will be loaded.
{% endstep %}

{% step %}
### Start an interactive query session

Use the CLI to ask questions and receive generated answers augmented by retrieved context.
{% endstep %}
{% endstepper %}

### Programmatic Usage

```python
from rag_system import RAGSystem

# Initialize
rag = RAGSystem(
    embedding_model="sentence-transformers/all-MiniLM-L6-v2",
    vector_store_path="vector_store",
    llm_model="llama3.1:8b"
)

# Load or create vector store
documents = rag.load_documents(["doc1.txt", "doc2.txt"])
rag.create_vector_store(documents, save=True)

# Query
result = rag.query("What is RAG?", k=5)
print(result['answer'])
```

## Architecture

```
Documents → Text Split → Embeddings → Vector Store (FAISS)
                                              ↓
                                         Retrieval
                                              ↓
                                         Generation (LLM)
```

## Configuration

### Environment Variables

```bash
RAG_EMBEDDING_MODEL=sentence-transformers/all-MiniLM-L6-v2
RAG_VECTOR_STORE_PATH=vector_store
RAG_LLM_MODEL=llama3.1:8b
OLLAMA_BASE_URL=http://localhost:11434
RAG_CHUNK_SIZE=1000
RAG_CHUNK_OVERLAP=200
RAG_DEFAULT_K=5
```

### Embedding Models

**Recommended Models:**

* `all-MiniLM-L6-v2` (default, fast, 384 dims)
* `all-mpnet-base-v2` (better quality, 768 dims)
* `all-MiniLM-L12-v2` (larger, 384 dims)

### LLM Integration

**Ollama (Local, Free):**

```bash
ollama pull llama3.1:8b

# Set RAG_LLM_MODEL=llama3.1:8b
```

**OpenAI (Cloud, Paid):**

```bash
export OPENAI_API_KEY=sk-...

# Use OpenAI models in generation
```

## Usage Examples

### Example 1: Simple Query

```python
rag = RAGSystem()
rag.load_vector_store()
result = rag.query("What is machine learning?")
print(result['answer'])
```

### Example 2: Custom Configuration

```python
rag = RAGSystem(
    embedding_model="sentence-transformers/all-mpnet-base-v2",
    chunk_size=1500,
    chunk_overlap=300
)
```

### Example 3: Adding Your Own Documents

```python
file_paths = [
    "documents/my_doc1.txt",
    "documents/my_doc2.md",
    "documents/data.json"
]
documents = rag.load_documents(file_paths)
rag.create_vector_store(documents, save=True)
```

## File Structure

```
RAG_Model/
├── rag_system.py      # Core RAG implementation
├── main.py            # CLI interface
├── config.py          # Configuration management
├── requirements.txt   # Dependencies
├── README.md          # Detailed documentation
├── documents/         # Your documents go here
└── vector_store/      # Generated vector store
```

## API Reference

### RAGSystem Class

#### `__init__(embedding_model, vector_store_path, llm_model, chunk_size, chunk_overlap)`

Initialize the RAG system.

#### `load_documents(file_paths) -> List[str]`

Load documents from file paths.

#### `create_vector_store(documents, save=True)`

Create vector store from documents.

#### `load_vector_store()`

Load existing vector store.

#### `retrieve(query, k=5) -> List[Dict]`

Retrieve relevant documents for a query.

#### `generate(query, k=5) -> str`

Generate answer using RAG.

#### `query(query, k=5) -> Dict`

Complete RAG query: retrieve and generate.

## Performance Tips

1. **Chunk Size**: 500-2000 tokens (adjust based on documents)
2. **Overlap**: 10-20% overlap for better context
3. **Top-K**: Start with k=5, adjust based on results
4. **Embedding Model**: Larger = better quality but slower
5. **Vector Store**: Use GPU FAISS for large datasets

## Troubleshooting

<details>

<summary>Import Errors</summary>

```bash
pip install langchain faiss-cpu sentence-transformers
```

</details>

<details>

<summary>Ollama Connection</summary>

```bash
# Check if Ollama is running
curl http://localhost:11434/api/tags

# Start Ollama
ollama serve
```

</details>

<details>

<summary>Memory Issues</summary>

* Reduce chunk size
* Use smaller embedding model
* Process documents in batches

</details>

## Advanced Usage

### Custom Embeddings

```python
from sentence_transformers import SentenceTransformer

# Use custom model
model = SentenceTransformer("your-model")
embeddings = model.encode(texts)
```

### Multiple Vector Stores

```python
# Create separate stores for different document sets
rag1 = RAGSystem(vector_store_path="store1")
rag2 = RAGSystem(vector_store_path="store2")
```

### Batch Processing

```python
# Process multiple document sets
for doc_set in document_sets:
    documents = rag.load_documents(doc_set)
    rag.create_vector_store(documents, save=False)
    # Process queries
```

## References

* [RAG Paper](https://arxiv.org/abs/2005.11401)
* [FAISS Documentation](https://github.com/facebookresearch/faiss)
* [Sentence Transformers](https://www.sbert.net/)
* [Ollama](https://ollama.ai/)

## Related Documentation

* [Installation Guide](/broken/pages/1ef7fbd556340561c91ecdefb653c9fccf8867a9)
* [Configuration Guide](/broken/pages/188b94520c748ba0fcc9ef6682a13b7689110cb0)
* [API Reference](/broken/pages/b929a48ccc84fcc44229713d8b2871ff7f2df3ec)
