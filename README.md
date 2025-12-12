# Langchain-rag-with-pdf
# 🧠 IT Helpdesk RAG Chatbot

A Retrieval-Augmented Generation (RAG) project that builds an intelligent question-answering assistant using an IT Helpdesk knowledge base stored in CSV format. It utilizes **LangChain**, **FAISS**, and **Hugging Face** models to answer user queries with high context accuracy.

---

## 📂 Dataset

* **Source**: Custom IT Helpdesk Knowledge Base (`data csv.csv`)
* **Description**: Contains structured helpdesk articles including topics, detailed steps, and ground truth answers.
* **Attributes**:
    * `ki_topic`: The subject of the issue (e.g., "Resetting a Forgotten PIN").
    * `ki_text`: Detailed resolution steps.
    * `sample_question` & `sample_ground_truth`: Pairs used for validation.

---

## 🛠️ Technologies Used

* **Language**: Python
* **Libraries**:
    * `pandas` for data manipulation and previewing.
    * `langchain` for building the RAG pipeline and orchestration.
    * `faiss-cpu` for efficient vector storage and similarity search.
    * `huggingface_hub` & `transformers` for LLM and Embeddings.

* **Models**:
    * **LLM**: `google/gemma-2b-it` (via Hugging Face Pipeline).
    * **Embeddings**: `sentence-transformers/all-MiniLM-L6-v2`.

---

## ✨ Key Features

✅ **Data Ingestion**
* Automated loading of CSV data using `CSVLoader`.
* Document splitting for efficient processing.

✅ **Vectorization**
* Conversion of textual data into vector embeddings using Hugging Face.
* Utilization of `all-MiniLM-L6-v2` for lightweight, fast embedding generation.

✅ **Vector Database**
* Implementation of **FAISS (Facebook AI Similarity Search)** for high-speed dense vector retrieval.
* In-memory document storage for local execution.

✅ **RAG Pipeline**
* **Retriever**: Fetches relevant context based on user queries.
* **Generation**: Passes context + query to the LLM (`Gemma-2b`) to synthesize a natural language response.

---

## 📊 Results

* **Contextual Accuracy**: The system successfully retrieves specific steps (e.g., *how to reset a PIN*) from the CSV and ignores irrelevant data.
* **Local Execution**: Runs entirely using `faiss-cpu` and open-source Hugging Face models, removing the need for paid external APIs like OpenAI for this specific implementation.

---

## 🚀 Getting Started

1.  **Clone the Repo**:
    ```bash
    git clone [https://github.com/yourusername/your-repo.git](https://github.com/yourusername/your-repo.git)
    ```

2.  **Install Dependencies**:
    ```bash
    pip install faiss-cpu langchain langchain-community langchain-huggingface pandas python-dotenv
    ```

3.  **Run the Notebook**:
    Open `rag with csv.ipynb` in Jupyter Notebook or Google Colab and run the cells to build the vector index and start chatting with your data.
