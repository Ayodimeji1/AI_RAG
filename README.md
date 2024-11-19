
# RAG Framework for Query Processing

## Table of Contents
- [Introduction](#introduction)
- [Project Structure](#project-structure)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Dependencies](#dependencies)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

---

## Introduction
This project provides a collection of tools for implementing and testing various Retrieval-Augmented Generation (RAG) techniques to process and enhance queries for document retrieval tasks. The framework is organized into three subprojects, each targeting a specific approach for query management:
1. **Simple Query**: Basic query-based document retrieval.
2. **Augmenting the Query**: Enhancing queries by generating related sub-queries.
3. **Multi-query**: Using multiple queries to combine information for improved retrieval and analysis.

## Project Structure
```
project-root/
│
├── simple_query/        # Basic RAG implementation
│   ├── expansion_answer.py
│   └── README.md        # Detailed explanation for Simple Query
│
├── augmenting_query/    # Augmented query RAG implementation
│   ├── expansion_queries.py
│   └── README.md        # Documentation for Augmenting the Query
│
├── multi_query/         # Multi-query RAG implementation
│   ├── reranking.py
│   └── README.md        # Documentation for Multi-query
│
├── data/                # Folder for storing PDF documents
│
└── README.md            # Main project documentation (this file)
```

## Features
- **Simple Query**:
  - Basic retrieval of documents based on single query input.
  - Embeds text and retrieves the most relevant results from ChromaDB.
- **Augmented Query**:
  - Enhances original queries with additional contextually relevant sub-queries using OpenAI GPT models.
  - Retrieves and ranks documents based on augmented queries.
- **Multi-query**:
  - Combines multiple queries (original and generated) to maximize information coverage.
  - Reranks results using relevance scoring with cross-encoders.
  - Supports embedding visualization and multi-query analysis.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/rag-framework.git
   cd rag-framework
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up environment variables:
   - Create a `.env` file in the root directory.
   - Add your OpenAI API key:
     ```
     OPENAI_API_KEY=your-api-key
     ```

## Usage
### Workflow
1. **Simple Query**:
   - Navigate to the `simple_query/` folder and run:
     ```bash
     python expansion_answer.py
     ```
   - This module retrieves documents based on a single input query.

2. **Augmenting the Query**:
   - Navigate to the `augmenting_query/` folder and run:
     ```bash
     python expansion_queries.py
     ```
   - This module generates and executes augmented queries for improved retrieval.

3. **Multi-query**:
   - Navigate to the `multi_query/` folder and run:
     ```bash
     python reranking.py
     ```
   - This module combines multiple queries, deduplicates results, and reranks them based on relevance scores.

## Dependencies
The project relies on the following libraries:
- `openai`
- `chromadb`
- `umap-learn`
- `pandas`
- `numpy`
- `langchain`
- `sentence-transformers`
- `matplotlib`
- `python-dotenv`
- `pypdf`

## Configuration
- **Environment Variables**: Store sensitive credentials like OpenAI API keys in a `.env` file.
- **Data Storage**: Place all PDF files to be processed in the `data/` folder.

## Contributing
Contributions are welcome! Please open issues or submit pull requests to enhance the framework.

## License
This project is licensed under the [MIT License](LICENSE).

---
