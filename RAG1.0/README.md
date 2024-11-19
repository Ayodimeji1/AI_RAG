
# Project Title: Document Embedding and Querying System

## Introduction

This project provides a pipeline for embedding, storing, and querying textual documents using OpenAI's embedding models and ChromaDB for persistent storage. The system allows for document ingestion, text chunking, embedding generation, and retrieval of relevant content in response to user queries.

The primary use case is building a question-answering system that retrieves context-relevant information from a document repository and generates concise answers using OpenAI's GPT models.

---

## Table of Contents

1. [Features](#features)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Dependencies](#dependencies)
5. [Configuration](#configuration)
6. [Examples](#examples)
7. [Troubleshooting](#troubleshooting)
8. [Contributors](#contributors)
9. [License](#license)

---

## Features

- **Environment Configuration:** Uses `.env` files to manage API keys.
- **Document Management:** Load and preprocess textual documents from a folder.
- **Text Chunking:** Splits large documents into manageable chunks for embedding.
- **Embedding Generation:** Leverages OpenAI API to generate text embeddings.
- **Persistent Storage:** Uses ChromaDB for storing embeddings and metadata.
- **Querying:** Retrieves contextually relevant document chunks for a given query.
- **Answer Generation:** Generates concise responses using GPT-based models.

---

## Installation

### Prerequisites
- Python 3.8 or higher
- `pip` (Python package manager)

### Steps

1. Clone the repository:
   ```bash
   git clone <repository_url>
   cd <repository_name>
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up your environment variables:
   - Create a `.env` file in the root directory.
   - Add the OpenAI API key:
     ```
     OPENAI_API_KEY=your_openai_api_key
     ```

4. Install ChromaDB and related libraries:
   ```bash
   pip install chromadb
   ```

---

## Usage

1. **Prepare Documents**:
   - Place your `.txt` documents in a folder (default: `./news_articles`).

2. **Run the Script**:
   Execute the main script to load documents, generate embeddings, and store them in the database:
   ```bash
   python main.py
   ```

3. **Query the System**:
   Modify the script to input your query:
   ```python
   question = "What is Databricks?"
   relevant_chunks = query_documents(question)
   answer = generate_response(question, relevant_chunks)
   print(answer)
   ```

---

## Dependencies

- `dotenv`: For loading environment variables.
- `openai`: For embedding and chat completion API calls.
- `chromadb`: For storing and querying embeddings.
- Other Python libraries: `os`, `json`, `requests`.

---

## Configuration

- **Environment Variables**:
  - Configure your `.env` file to include:
    ```plaintext
    OPENAI_API_KEY=your_api_key
    ```
- **Document Path**:
  - Update the `folder_path` variable in the script if your documents are in a different location.

---

## Examples

### Loading Documents
Documents are loaded from the specified folder path:
```plaintext
Loaded 10 documents
```

### Querying the System
Input a question, and the system retrieves relevant document chunks and generates an answer:
```plaintext
Question: What is Databricks?
Answer: Databricks is a unified analytics platform known for its big data and AI solutions.
```

---

## Troubleshooting

- **Error: `API key not found`**:
  Ensure the `.env` file is configured correctly with the OpenAI API key.

- **ChromaDB storage issues**:
  - Verify the path specified for persistent storage is writable.

- **Performance Issues**:
  - Use smaller chunk sizes if the system takes too long to process large documents.

---

## Contributors

- **Your Name** - Developer
- Open for contributions! Feel free to submit a pull request.

---

## License

This project is licensed under the [MIT License](LICENSE).

---

Feel free to reach out for support or contribute to enhance the project! 🚀
