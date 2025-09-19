# Advanced Strategies for RAG Models

This project contains a series of Jupyter notebooks that explore and implement various advanced retrieval and re-ranking techniques to improve the performance of Retrieval-Augmented Generation (RAG) systems.

## Project Overview

This project goes beyond basic vector search to implement more advanced methods:

- **Hybrid Search:** Combines the strengths of dense (vector-based) and sparse (keyword-based) retrievers.
- **Fusion Retriever:** Merges results from multiple retrievers into a single unified ranking.
- **Query Transformations:** Rewrites queries or generates hypothetical documents for better retrieval results.
- **Re-ranking:** Implements a cross-encoder to improve the relevance of retrieved documents.

## Notebooks

### 1. `other_techniques.ipynb`

This notebook implements and evaluates various retrieval enhancement techniques for a RAG pipeline.

- **Features:**
    - **HyDE (Hypothetical Document Embeddings):** Generates a hypothetical document in response to a query and uses its embedding to find relevant documents.
    - **Query Rewriting:** Reformulates the original query for better retrieval performance.
    - **Re-ranking:** Uses a `CrossEncoder` model to improve the order of retrieved documents.
- **Evaluation:**
    - Uses `DeepEval` to evaluate the faithfulness and relevance of the RAG pipeline.

### 2. `hybrid_rag.ipynb`

This notebook creates a hybrid retrieval system that combines both keyword-based (sparse) and semantic (dense) retrievers.

- **Features:**
    - **BM25 Retriever:** A sparse retriever for keyword matching.
    - **FAISS Retriever:** A dense vector store for semantic similarity.
    - **EnsembleRetriever:** Combines the results from BM25 and FAISS.
    - **Re-ranking:** Further improves relevance with a `CrossEncoder`.
- **Evaluation:**
    - Uses `DeepEval` to measure the performance of the hybrid RAG system.

### 3. `fusion_retriever.ipynb`

This notebook implements a custom fusion retriever that combines the results from BM25 and a vector retriever.

- **Features:**
    - **BM25 and FAISS:** Generate results from two different types of retrievers.
    - **Custom Fusion Logic:** Normalizes and combines the scores from the two retrievers.
    - The results are ranked based on a combined score.

## Setup and Usage

1.  **Install Dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

2.  **Environment Variables:**
    - Create a `.env` file in the project root directory.
    - Add your Google API key to the `.env` file:
        ```
        GOOGLE_API_KEY="YOUR_API_KEY"
        ```

3.  **Run the Notebooks:**
    - Start Jupyter Lab or Jupyter Notebook:
        ```bash
        jupyter lab
        ```
    - Open the desired notebook (`other_techniques.ipynb`, `hybrid_rag.ipynb`, or `fusion_retriever.ipynb`) and run the cells.