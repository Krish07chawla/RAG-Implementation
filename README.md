# RAG Implementation 🚀

An implementation of **Retrieval-Augmented Generation (RAG)** using Python, LangChain, ChromaDB, and multiple Large Language Models (LLMs), including OpenAI, Groq, and Google Gemini.

This project demonstrates how to retrieve relevant information from documents using vector embeddings and generate context-aware answers with LLMs.

## 📌 Project Overview

Large Language Models can sometimes produce incorrect or unsupported answers. Retrieval-Augmented Generation helps address this problem by retrieving relevant information from a knowledge base and providing it as context to an LLM.

This project implements a basic RAG pipeline that combines document retrieval with LLM-based answer generation.

## ✨ Features

- **Document Retrieval:** Retrieve relevant document chunks based on a user's query.
- **Text Embeddings:** Convert text into numerical vector representations.
- **Vector Database:** Store and search document embeddings using ChromaDB.
- **Multiple LLM Providers:** Integrate OpenAI, Groq, and Google Gemini.
- **Semantic Search:** Retrieve documents based on vector similarity.
- **Context-Aware Generation:** Generate answers using retrieved document context.
- **Reusable Pipeline:** Use the same RAG function with different LLM providers.

## 🛠️ Technologies Used

- Python
- Google Colab
- LangChain
- ChromaDB
- Sentence Transformers
- OpenAI API
- Groq API
- Google Gemini API

## 🔄 RAG Architecture

The pipeline follows these steps:

1. **Document Loading:** Load the source documents.
2. **Text Chunking:** Split documents into smaller chunks.
3. **Embedding Generation:** Convert the chunks into vector embeddings.
4. **Vector Storage:** Store embeddings and document text in ChromaDB.
5. **Query Embedding:** Convert the user's question into an embedding.
6. **Document Retrieval:** Retrieve the most relevant document chunks.
7. **Context Preparation:** Combine retrieved chunks into a context.
8. **Answer Generation:** Pass the context and question to an LLM.
9. **Final Response:** Return the generated answer to the user.

## 🧠 Supported LLM Providers

| Provider | Purpose |
|---|---|
| OpenAI | Generate answers using an OpenAI model |
| Groq | Generate answers using a Groq-hosted model |
| Google Gemini | Generate answers using a Gemini model |

The same retrieval pipeline can be reused across providers, making it possible to compare their responses using the same query and retrieved context.

## 📂 Project Structure

```text
RAG-Implementation/
│
├── RAGipynb (1).ipynb
└── README.md
```

The notebook contains the implementation of the RAG pipeline.

## ⚙️ Setup and Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/RAG-Implementation.git
cd RAG-Implementation
```

Replace `YOUR-USERNAME` with your GitHub username.

### 2. Open the notebook

Open the notebook in Google Colab or run it in a suitable Python environment.

### 3. Install the required libraries

Install the dependencies used in the notebook:

```python
%pip install -q langchain langchain-community langchain-openai langchain-groq langchain-google-genai chromadb sentence-transformers pypdf
```

Additional packages may be required depending on the document-loading and text-splitting methods used.

### 4. Configure API keys

This project uses API keys to access the supported LLM providers.

For Google Colab, store your keys in **Colab Secrets** rather than writing them directly in the notebook.

Example secret names:

- `OPENAI_API_KEY`
- `GROQ_API_KEY`
- `GEMINI_API_KEY`

Retrieve a key securely in Colab:

```python
from google.colab import userdata

OPENAI_API_KEY = userdata.get("OPENAI_API_KEY")
```

Use the corresponding secret name when retrieving the Groq or Gemini key.

**Security:** Never commit API keys, passwords, or other credentials to GitHub.

## 💬 Example Usage

Once the notebook has initialized the document retriever and LLM, a question can be passed to the RAG pipeline:

```python
answer = generate_output(
    "What is encoder-decoder?",
    rag_retriever,
    gemini_llm
)

print(answer)
```

The same function can be used with other initialized model instances, such as OpenAI or Groq.

## 🎯 Learning Objectives

This project explores:

- The fundamentals of Retrieval-Augmented Generation.
- Text embeddings and semantic similarity.
- Vector databases and document retrieval.
- Integration of multiple LLM APIs.
- Context construction and prompt engineering.
- Reusable components in a RAG pipeline.

## 🚀 Future Improvements

- Improve retrieval accuracy and document chunking.
- Add source citations to generated answers.
- Evaluate retrieval quality and answer faithfulness.
- Compare LLMs using consistent evaluation questions.
- Add a user interface for uploading documents and asking questions.
- Explore advanced retrieval techniques and reranking.

## 👨‍💻 Author

**Krish Chawla**

B.Tech Computer Science Student

---

*This project was developed for learning and experimentation with Retrieval-Augmented Generation and Large Language Models.*
