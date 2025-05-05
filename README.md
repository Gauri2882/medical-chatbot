# MediBot - AI Medical Chatbot using RAG


A modern AI chatbot for medical documents using Retrieval Augmented Generation (RAG) technology.


<p align="center">
  <img src="https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/LangChain-00A67E?logo=langchain&logoColor=white" alt="LangChain">
  <img src="https://img.shields.io/badge/HuggingFace-FFD21E?logo=huggingface&logoColor=black" alt="HuggingFace">
  <img src="https://img.shields.io/badge/FAISS-5C3EE8?logo=facebook&logoColor=white" alt="FAISS">
  <img src="https://img.shields.io/badge/Streamlit-FF4B4B?logo=streamlit&logoColor=white" alt="Streamlit">
</p>

## Project Overview

MediBot is a modular 3-phase chatbot project that allows users to query medical documents through a conversational interface. The system leverages state-of-the-art language models and vector database technology to provide accurate, context-aware responses.

## Project Layout

### Phase 1 – Setup Memory for LLM (Vector Database)
- Load raw PDF(s)
- Create document chunks
- Generate vector embeddings
- Store embeddings in FAISS vector database

### Phase 2 – Connect Memory with LLM
- Setup LLM (Mistral via HuggingFace)
- Connect LLM with FAISS vector store
- Create processing chain

### Phase 3 – Setup UI for the Chatbot
- Develop chatbot interface with Streamlit
- Load vector store (FAISS) in cache
- Implement Retrieval Augmented Generation (RAG) pipeline

## Tools & Technologies

- **Langchain** - AI Framework for LLM applications
- **HuggingFace** - ML/AI Hub for models and datasets
- **Mistral** - Large Language Model
- **FAISS** - Vector Database for efficient similarity search
- **Streamlit** - For building the chatbot UI
- **Python** - Primary programming language
- **VS Code** - Integrated Development Environment

## Technical Architecture
```mermaid
flowchart TD
    A[User Input] --> B[Streamlit UI]
    B --> C[LangChain]
    C --> D[Mistral LLM]
    D -->|HuggingFace| C
    C --> E[FAISS Vector DB]
    E --> F[PDF Documents]
    F --> G[Chunking]
    G --> H[Embeddings]
    H --> E
    C --> I[Response]
    I --> B
```
### Prerequisites
- Python 3.8+
- Pipenv
- [HuggingFace account](https://huggingface.co/join)

### Installation

```bash
git clone https://github.com/Gauri2882/medical-chatbot.git
cd medical-chatbot
pipenv install langchain langchain_community langchain_huggingface faiss-cpu pypdf
pipenv install huggingface_hub
pipenv install streamlit
pipenv shell
streamlit run medibot.py
```

## Summary

MediBot represents a modern approach to document interaction:
- Modular 3-phase implementation
- Utilizes cutting-edge technologies:
  - Streamlit | Langchain | HuggingFace
  - Retrieval Augmented Generation (RAG)
  - Vector Embeddings
  - End-to-end RAG pipeline
