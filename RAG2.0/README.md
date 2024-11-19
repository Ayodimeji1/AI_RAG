
# Document Processing and Query Augmentation Framework

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
This project provides a framework for processing and analyzing textual data from PDF documents, leveraging advanced text-splitting and embedding techniques to support query-driven data exploration. It uses OpenAI's GPT models and ChromaDB to enhance document query capabilities and streamline information retrieval.

## Features
- **PDF Text Extraction**: Extracts text from PDF files.
- **Text Chunking**: Splits text into manageable chunks using recursive character and token-based strategies.
- **Embeddings and Dimensionality Reduction**: Generates sentence embeddings and visualizes them using UMAP projections.
- **Query Augmentation**: Enhances user queries with generated context from GPT models.
- **ChromaDB Integration**: Stores and retrieves document embeddings for efficient querying.
- **Customizable Models**: Integrates GPT-3.5-turbo for generating augmented queries.

## Installation
1. Clone this repository:
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
### Processing a PDF
1. Place your PDF in the `data/` folder (e.g., `data/microsoft-annual-report.pdf`).
2. Run the script:
   ```bash
   python expansion_answer.py
   ```
3. Outputs include:
   - Chunked text
   - Generated query responses
   - Retrieved documents from ChromaDB

### Augmenting a Query
You can augment your query by calling:
```python
from expansion_answer import augment_query_generated
response = augment_query_generated("Your query here")
print(response)
```

### Custom Embeddings
To add custom documents to the database:
```python
from helper_utils import load_chroma
collection = load_chroma("path/to/pdf", "collection_name", embedding_function)
```

## Dependencies
- **Python Libraries**:
  - `openai`
  - `chromadb`
  - `umap-learn`
  - `pandas`
  - `numpy`
  - `langchain`
  - `pypdf`
  - `python-dotenv`
- **ChromaDB**: For managing and querying document embeddings.
- **OpenAI GPT Models**: For query augmentation.

## Configuration
Ensure the following configurations:
- **API Keys**: Store sensitive credentials like OpenAI keys in the `.env` file.
- **Data Storage**: PDF files should be placed in the `data/` folder.

## Contributing
Contributions are welcome! Feel free to open issues or submit pull requests to enhance the project.

## License
This project is licensed under the [MIT License](LICENSE).

---
