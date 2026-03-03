# 🤖 Conversational RAG Q&A Chatbot with PDF Upload

<div align="center">

![Python](https://img.shields.io/badge/Python-3.12-blue.svg)
![Streamlit](https://img.shields.io/badge/Streamlit-1.54.0-FF4B4B.svg)
![LangChain](https://img.shields.io/badge/LangChain-0.3.14-green.svg)
![License](https://img.shields.io/badge/License-MIT-yellow.svg)

**An intelligent chatbot that answers questions from your PDF documents with conversation history!**

[Features](#-features) • [Demo](#-demo) • [Installation](#-installation) • [Usage](#-usage) • [Tech Stack](#-tech-stack)

</div>

---

## 📋 Overview

This is a **Retrieval-Augmented Generation (RAG)** based conversational Q&A system that allows users to upload PDF documents and ask questions about their content. The chatbot maintains conversation history and provides contextually relevant answers using advanced AI models.

## ✨ Features

- 📄 **PDF Upload Support**: Upload multiple PDF documents simultaneously
- 💬 **Conversational AI**: Maintains chat history for context-aware responses
- 🧠 **RAG Architecture**: Combines document retrieval with language generation
- 🎯 **Accurate Answers**: Powered by Groq's high-performance LLM
- 🔒 **Session Management**: Each conversation has its own isolated session
- 🚀 **Fast Processing**: Efficient document chunking and vector embeddings
- 🎨 **User-Friendly Interface**: Built with Streamlit for easy interaction

## 🎬 Demo

1. Enter your Groq API key
2. Upload one or more PDF files
3. Ask questions about the content
4. Get intelligent, context-aware answers!

## 🛠️ Tech Stack

### Core Technologies
- **[Streamlit](https://streamlit.io/)** - Web application framework
- **[LangChain](https://python.langchain.com/)** - LLM orchestration framework
- **[Groq](https://groq.com/)** - High-performance LLM inference
- **[ChromaDB](https://www.trychroma.com/)** - Vector database for embeddings
- **[HuggingFace](https://huggingface.co/)** - Embeddings models

### Key Components
- **Document Loader**: PyPDFLoader for PDF processing
- **Text Splitter**: Recursive character text splitter for optimal chunking
- **Embeddings**: HuggingFace's `all-MiniLM-L6-v2` model
- **Vector Store**: ChromaDB for semantic search
- **LLM**: Groq's GPT-OSS-120B model

## 📦 Installation

### Prerequisites
- Python 3.12 or higher
- Groq API key ([Get one here](https://console.groq.com/))
- HuggingFace Token (optional, for embeddings)

### Step 1: Clone the Repository
```bash
git clone https://github.com/yourusername/rag-chatbot.git
cd rag-chatbot
```

### Step 2: Create Virtual Environment
```bash
python -m venv venv

# On Windows
venv\Scripts\activate

# On macOS/Linux
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

### Step 4: Set Up Environment Variables
Create a `.env` file in the project root:
```env
HF_TOKEN=your_huggingface_token_here
```

## 🚀 Usage

### Running the Application
```bash
streamlit run app.py
```

Or using Python module:
```bash
python -m streamlit run app.py
```

The application will open in your default browser at `http://localhost:8501`

### Using the Chatbot

1. **Enter API Key**: Paste your Groq API key in the input field
2. **Set Session ID**: Use the default or create a custom session identifier
3. **Upload PDFs**: Click "Browse files" and select one or more PDF documents
4. **Ask Questions**: Type your question in the input box
5. **View Responses**: The AI will provide answers based on your documents

### Example Questions
- "What is the main topic of this document?"
- "Can you summarize the key points?"
- "What does the document say about [specific topic]?"

## 📁 Project Structure

```
2_QnA_Chatbot_Rag/
├── app.py                 # Main Streamlit application
├── requirements.txt       # Python dependencies
├── .env                   # Environment variables (create this)
├── README.md             # Project documentation
└── temp.pdf              # Temporary file for PDF processing
```

## 🔧 Configuration

### Adjustable Parameters

In `app.py`, you can modify:

```python
# Text splitting parameters
chunk_size = 5000          # Size of each text chunk
chunk_overlap = 500        # Overlap between chunks

# Embedding model
model_name = "all-MiniLM-L6-v2"

# LLM model
model = "openai/gpt-oss-120b"
```

## 📚 How It Works

1. **Document Processing**: PDFs are loaded and split into manageable chunks
2. **Embedding Creation**: Text chunks are converted to vector embeddings
3. **Vector Storage**: Embeddings are stored in ChromaDB for fast retrieval
4. **Query Processing**: User questions are converted to embeddings
5. **Retrieval**: Relevant document chunks are retrieved based on similarity
6. **Answer Generation**: LLM generates answers using retrieved context
7. **History Management**: Conversation history is maintained for context

## 🔐 Security Notes

- Never commit your `.env` file or API keys to version control
- Add `.env` to your `.gitignore` file
- Keep your API keys secure and rotate them regularly

## 🐛 Troubleshooting

### Common Issues

**ImportError: cannot import name 'ModelProfile'**
```bash
pip uninstall langchain langchain_core langchain_community -y
pip install -r requirements.txt
```

**Streamlit not found**
```bash
python -m pip install streamlit
```

**CUDA/GPU Issues**
- The app works on CPU, GPU is not required
- If you have GPU issues, ensure PyTorch is properly installed

## 🤝 Contributing

Contributions are welcome! Please feel free to submit a Pull Request.

1. Fork the project
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [LangChain](https://github.com/langchain-ai/langchain) for the amazing framework
- [Streamlit](https://github.com/streamlit/streamlit) for the intuitive UI
- [Groq](https://groq.com/) for fast LLM inference
- [HuggingFace](https://huggingface.co/) for embeddings models

## 📧 Contact

Your Name - [@yourtwitter](https://twitter.com/yourtwitter)

Project Link: [https://github.com/yourusername/rag-chatbot](https://github.com/yourusername/rag-chatbot)

---

<div align="center">

**⭐ Star this repo if you find it helpful!**

Made with ❤️ using Python and LangChain

</div>
