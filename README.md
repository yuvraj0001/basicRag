# BasicRAG

A Retrieval-Augmented Generation (RAG) application that allows you to query your PDF documents using natural language. Built with LangChain, ChromaDB, and Groq LLM.

## What it does
Upload your PDF documents and ask questions in plain English. The application finds the most relevant sections from your documents and uses an LLM to generate accurate, context-aware answers.

## Tech Stack
- **LangChain** — document loading and text splitting
- **SentenceTransformers** — generating document embeddings
- **ChromaDB** — vector database for storing and searching embeddings
- **Groq LLM** — fast inference for generating responses
- **uv** — Python package management

## How it works
1. PDFs are loaded and split into smaller chunks
2. Each chunk is converted into embeddings (vectors)
3. Embeddings are stored in ChromaDB
4. User query is converted to an embedding
5. Most similar chunks are retrieved from ChromaDB
6. Retrieved chunks + query are sent to Groq LLM
7. LLM generates a final answer

## Setup

**1. Clone the repository**
```bash
git clone https://github.com/yuvraj0001/basicRag.git
cd basicRag
```

**2. Create virtual environment**
```bash
uv venv
source .venv/bin/activate  # Mac/Linux
.venv\Scripts\activate     # Windows
```

**3. Install dependencies**
```bash
uv sync
```

**4. Set up environment variables**

Create a `.env` file in the root directory:

GROQ_API_KEY=your_groq_api_key_here

**5. Add your PDFs**

Place your PDF files in the `data/` directory.

**6. Run the notebook**

Open `main.ipynb` and run all cells.

## Project Structure

basicRag/
├── data/              # PDF files and vector store
├── main.ipynb         # Main notebook
├── pyproject.toml     # Project dependencies
├── .env               # API keys (not committed to git)
└── README.md

## Getting a Groq API Key
1. Go to [console.groq.com](https://console.groq.com)
2. Sign up for a free account
3. Generate an API key
4. Add it to your `.env` file