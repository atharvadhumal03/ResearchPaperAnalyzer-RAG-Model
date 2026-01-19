# Research Paper Analyzer - RAG Model

A Retrieval-Augmented Generation (RAG) system for analyzing research papers using natural language queries. This project demonstrates the implementation of a complete RAG pipeline that can load PDF research papers, process them into semantic chunks, and answer questions about their content using AI.

## 🎯 Project Overview

This project implements a RAG-based question-answering system specifically designed for academic research papers. Users can upload research papers in PDF format and ask natural language questions to extract insights, summaries, and specific information from the documents.

## 🚀 Features

- **PDF Processing**: Automatic loading and parsing of research papers
- **Intelligent Chunking**: Smart text segmentation for optimal context retrieval
- **Semantic Search**: Vector-based similarity search using HuggingFace embeddings
- **AI-Powered Responses**: Integration with Google's Gemini LLM for natural language answers
- **Persistent Storage**: ChromaDB vector database for efficient embedding storage
- **Local Embeddings**: Free, unlimited HuggingFace embeddings running locally

## 🛠️ Technology Stack

- **Python 3.13**
- **LangChain**: Framework for building LLM applications
- **Google Gemini 2.5 Flash**: Large Language Model for generation
- **HuggingFace**: Sentence transformers for embeddings (all-MiniLM-L6-v2)
- **ChromaDB**: Vector database for semantic search
- **PyPDF**: PDF document processing
- **Jupyter Notebook**: Development and experimentation environment

## 📋 Prerequisites

- Python 3.10+
- Google Gemini API key ([Get one here](https://aistudio.google.com/welcome?utm_source=google&utm_medium=cpc&utm_campaign=Cloud-SS-DR-AIS-FY26-global-gsem-1713578&utm_content=text-ad&utm_term=KW_gemini%20api%20key&gad_source=1&gad_campaignid=23417416052&gbraid=0AAAAACn9t67hhz7im3Dctot35upp57uzL&gclid=CjwKCAiAybfLBhAjEiwAI0mBBvy1yf94ChC1E4ZyJEjvskG2pv3_IjF7DZXk52XmNuzhnm8EVHyyBBoCat8QAvD_BwE))
- Virtual environment (recommended)

## 🔧 Installation

1. **Clone the repository**
```bash
git clone https://github.com/yourusername/research-paper-rag-analyzer.git
cd research-paper-rag-analyzer
```

2. **Create and activate virtual environment**
```bash
python3 -m venv myVenv
source myVenv/bin/activate  # On Windows: myVenv\Scripts\activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Set up environment variables**
```bash
# Create .env file
touch .env

# Add your API key to .env
echo "GEMINI_API_KEY=your_api_key_here" > .env
```

## 📖 Usage

1. **Start Jupyter Notebook**
```bash
jupyter notebook
```

2. **Open `notebook.ipynb`**

3. **Place your research paper PDF** in the project directory

4. **Run the cells** to:
   - Load your API credentials
   - Process the PDF
   - Create embeddings
   - Query the paper

5. **Ask questions** about your paper:
```python
rag_chain.invoke("What is the main contribution of this paper?")
rag_chain.invoke("What methodology did the authors use?")
rag_chain.invoke("What are the key findings?")
```

## 🏗️ Project Structure
```
research-paper-rag-analyzer/
├── notebook.ipynb          # Main Jupyter notebook
├── README.md              # Project documentation
├── requirements.txt       # Python dependencies
├── .env                   # API keys (not in git)
├── .env.example          # Environment template
├── .gitignore            # Git ignore rules
├── myVenv/               # Virtual environment (not in git)
└── chroma_db/            # Vector database storage (not in git)
```

## 🔍 How It Works

1. **Document Loading**: PDF is loaded and split into pages using PyPDF
2. **Text Chunking**: Pages are split into overlapping chunks (1000 chars, 300 overlap)
3. **Embedding Generation**: Each chunk is converted to a 384-dimensional vector using HuggingFace
4. **Vector Storage**: Embeddings are stored in ChromaDB for fast retrieval
5. **Query Processing**: User questions are embedded and matched against stored chunks
6. **Answer Generation**: Retrieved context is sent to Gemini LLM for natural language response

## 🚢 Deployment (Coming Soon)

This project is designed to be deployed using Docker. Future updates will include:
- Streamlit web interface
- Docker containerization
- Cloud deployment options

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

## 👨‍💻 Author

**Atharva Dhumal**
- Graduate Student at Northeastern University
- Relevant Courses: CS5330 (CVPR), CS6120 (NLP), CS7150 (Deep Learning)

## ⭐️ Acknowledgments
- Inspired by the RAG paper: "Retrieval-Augmented Generation for Knowledge-Intensive NLP Tasks"

## 📧 Contact

For questions or feedback, please open an issue on GitHub.