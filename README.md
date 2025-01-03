
## Light-RAG Document Query System

<img width="949" alt="image" src="https://github.com/user-attachments/assets/35d07665-dbc9-4155-83a9-e633f52905a3" />
<img width="958" alt="image" src="https://github.com/user-attachments/assets/fde7a158-0e92-4b97-9943-90afac525678" />

This repository provides a **Document Query System** powered by **Light-RAG** (Lightweight Retrieval-Augmented Generation), Azure OpenAI APIs, and Streamlit. The application facilitates document ingestion and querying using advanced LLMs and embedding functions.

### Key Features
- **Document Ingestion**: Supports `.txt` and `.csv` files for ingestion, with automatic summarization for structured data.
- **Querying**: Allows users to perform **local**, **global**, and **hybrid** search queries across ingested documents.
- **Azure OpenAI Integration**: Utilizes Azure OpenAI for LLM-based summarization and embeddings.
- **Streamlit Interface**: Provides a user-friendly interface for uploading files and querying documents.

---

### Setup Instructions

#### Prerequisites
- Python 3.8 or higher.
- Azure OpenAI access with the following endpoints and keys configured in `.env` file:
  - **Chat Completions**
  - **Embeddings**

#### Environment Variables
Create a `.env` file with the following content:
```env
AZURE_OPENAI_API_KEY=<your-api-key>
AZURE_OPENAI_API_VERSION=<api-version>
AZURE_OPENAI_ENDPOINT=<api-endpoint>
AZURE_OPENAI_DEPLOYMENT=<deployment-name>

AZURE_EMBEDDING_API_KEY=<your-embedding-api-key>
AZURE_EMBEDDING_API_VERSION=<api-version>
AZURE_EMBEDDING_ENDPOINT=<api-endpoint>
AZURE_EMBEDDING_DEPLOYMENT=<embedding-deployment-name>
```

#### Installation
1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```
2. Install dependencies:
   ```bash
   pip install lightrag-hku
   ```

#### Running the Application
Start the Streamlit application:
```bash
streamlit run app.py
```

---

### Usage Guide

#### Document Ingestion
1. Upload `.txt` or `.csv` files via the **Document Ingestion** section.
2. For `.csv` files, the data is automatically summarized into concise paragraphs before ingestion.

#### Query Documents
1. Enter a query in the **Query Documents** section.
2. Choose a search type:
   - `local`: Search within specific documents.
   - `global`: Search across all documents.
   - `hybrid`: Combines local and global search results.
3. View query results in a structured format.

---

### Code Overview

1. **Ingestion**:
   - CSV files are summarized into narrative paragraphs using Azure OpenAI.
   - Text files are directly processed.
   - Content is ingested into the Light-RAG system in the form of relationships in json format
   - Note : You can also store the generated graphml & json files in MongoDB Cluster
   <img width="232" alt="image" src="https://github.com/user-attachments/assets/381eb2cf-0529-4bde-9510-22a8e8cf05f5" />


2. **Querying**:
   - Queries are executed using Light-RAG's `aquery` function.
   - Results are displayed in JSON or text format based on their structure.

3. **Integration**:
   - Azure OpenAI APIs handle LLM queries and embeddings.
   - `LightRAG` provides efficient document retrieval and query handling.

4. **Streamlit Interface**:
   - File upload and query submission are handled through an intuitive web interface.

---

### Dependencies
- **Streamlit**: For building the user interface.
- **LightRAG**: For lightweight RAG functionalities.
- **Azure OpenAI**: For LLM and embedding services.
- **Pandas**: For CSV processing.
- **NumPy**: For embedding array manipulation.

---

### Future Enhancements
- Data Visualization using Neo4j-DB for Admin Purposes
- Add support for additional file types (e.g., PDFs).
- Include advanced query filters and ranking.
- Expand embedding support for multilingual documents.

---

### Acknowledgments
This project uses **LightRAG** for efficient retrieval-augmented generation and **Azure OpenAI** for state-of-the-art LLM functionalities.
