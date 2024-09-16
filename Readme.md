# **LLM-Powered Document Retrieval System using FAISS and Streamlit**

This project is a web-based document retrieval system that leverages the power of **LangChain**, **FAISS**, and **OpenAI** for efficient semantic search and document retrieval. Users can input URLs of articles or documents, and the system processes, embeds, and indexes the text to allow for fast, intelligent search through natural language queries.

## **Table of Contents**

- [Features](#features)
- [Technologies](#technologies)
- [Installation](#installation)
- [Usage](#usage)
- [Project Flow](#project-flow)
- [File Structure](#file-structure)
- [User Interface](#user-interface)

## **Features**

- **Load and Process URLs**: Extracts text from URLs using `UnstructuredURLLoader`.
- **Text Chunking**: Automatically splits large text into smaller, manageable chunks for processing.
- **Embeddings**: Uses OpenAI’s API to create vector embeddings of the text chunks.
- **FAISS Indexing**: Efficiently indexes the text embeddings using FAISS for fast similarity search.
- **Real-time Question Answering**: Provides answers to user queries by retrieving the most relevant text chunks.
- **Interactive Web Interface**: Built using Streamlit, allowing users to interact with the system through a simple and intuitive UI.

## **Technologies**

- **Python 3.9+**
- **LangChain** for text processing and vectorization.
- **FAISS (Facebook AI Similarity Search)** for efficient similarity search on the document embeddings.
- **OpenAI** for generating text embeddings.
- **Streamlit** for building an interactive web application.
- **Unstructured** for text loading from URLs.
- **Pickle** for saving and loading FAISS indexes.

## **Installation**

1. **Clone the repository**:

   ```bash
   git clone https://github.com/your-repo-name.git
   cd your-repo-name
   ```

2. **Install the required packages**:
   Install dependencies listed in `requirements.txt`:

   ```bash
   pip install -r requirements.txt
   ```

3. **Set up API Keys**:
   - You need an OpenAI API key to generate embeddings. Create a `.env` file in the project root with your API key:
     ```
     OPENAI_API_KEY=your-openai-api-key
     ```

## **Usage**

1. **Run the Streamlit App**:

   ```bash
   streamlit run main.py
   ```

2. **Process URLs**:

   - In the Streamlit app, input URLs in the sidebar to process documents. The app will extract and split the text into chunks.

3. **Ask Questions**:
   - Once the text has been processed, input a query in the app to get the most relevant answers based on the FAISS similarity search.

## **Project Flow**

1. **Text Loading**: The project starts by loading text from the URLs you provide.
2. **Text Splitting**: The text is split into chunks using LangChain's `RecursiveCharacterTextSplitter` to ensure compatibility with language model token limits.
3. **Vector Embeddings**: Each text chunk is converted into a vector embedding using OpenAI’s API.
4. **FAISS Indexing**: The embeddings are stored in a FAISS index for fast similarity search.
5. **Querying**: When a user asks a question, it is converted into an embedding and the FAISS index is queried to retrieve the most relevant text chunks.
6. **Real-time Results**: The system displays the most relevant answers along with sources.

## **File Structure**

```
├── faiss_tutorial.ipynb            # Demonstrates FAISS indexing and retrieval
├── retrieval.ipynb                 # Notebook for document retrieval using FAISS
├── text_loaders_splitters.ipynb    # Handles text loading and splitting
├── main.py                         # The main Streamlit app script
├── requirements.txt                # Dependencies for the project
└── .env                            # Environment variables (not included in repo)
```

## **User Interface**

Here is a screenshot of the web application interface:

![UI Screenshot](Finbot.jpg)
