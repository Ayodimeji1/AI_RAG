
# Document Processing, Query Augmentation, and Reranking Framework

## Table of Contents
- [Introduction](#introduction)
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Dependencies](#dependencies)
- [Configuration](#configuration)
- [Contributing](#contributing)
- [License](#license)

---

## Introduction
This project provides a powerful framework for processing and analyzing textual data from PDF documents. It leverages advanced text-splitting, embedding, reranking, and query augmentation techniques. The framework integrates OpenAI's GPT models, ChromaDB, and UMAP for query-driven exploration, embedding visualizations, and document retrieval.

## Features
- **PDF Text Extraction**: Extracts text from PDF files using `PyPDF`.
- **Text Chunking**: Splits extracted text into chunks using character-based or token-based splitters.
- **Embeddings Management**: Generates and stores document embeddings using `SentenceTransformer` and ChromaDB.
- **Query Augmentation**: Enhances original user queries with contextually relevant additional queries.
- **Cross-Encoding Reranking**: Refines document relevance scores using a cross-encoder model.
- **Embedding Visualization**: Visualizes embeddings and query-document relationships using UMAP projections.
- **Multi-query Processing**: Combines original and augmented queries for comprehensive information retrieval.

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-repo/document-processing-framework.git
   cd document-processing-framework
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
### Processing and Storing Documents
1. Place your PDF in the `data/` folder (e.g., `data/microsoft-annual-report.pdf`).
2. Process the document and add it to the ChromaDB collection:
   ```python
   from helper_utils import load_chroma
   load_chroma("data/microsoft-annual-report.pdf", "microsoft-collect", embedding_function)
   ```

### Query Augmentation and Retrieval
1. Enhance a query with related sub-queries:
   ```python
   from expansion_queries import generate_multi_query
   augmented_queries = generate_multi_query("What were the main factors for revenue growth?")
   print(augmented_queries)
   ```

2. Retrieve and rank results:
   ```python
   from reranking import generate_multi_query
   context, final_results = generate_multi_query("What was the R&D expenditure?")
   print(final_results)
   ```

3. Visualize embeddings:
   - Utilize the UMAP-based embedding projection:
     ```python
     from helper_utils import project_embeddings
     projected = project_embeddings(embeddings, umap_transform)
     ```

### Multi-query Execution
Execute an original query with augmented queries to improve retrieval precision:
```python
from reranking import generate_multi_query
context = generate_multi_query("Describe the revenue growth details.")
```

## Dependencies
- **Python Libraries**:
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
- **ChromaDB**: Manages document embeddings.
- **OpenAI GPT Models**: Powers query augmentation and text analysis.

## Configuration
- **Environment Variables**: Store API keys (e.g., OpenAI) in a `.env` file.
- **Data**: Place PDF files in the `data/` folder for processing.

## Contributing
Contributions are welcome! Please open issues or submit pull requests for any enhancements or bug fixes.

## License
This project is licensed under the [MIT License](LICENSE).

---
