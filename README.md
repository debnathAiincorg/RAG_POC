# RAG_POC - Retrieval-Augmented Generation Proof of Concept

A Python-based proof of concept demonstrating Retrieval-Augmented Generation (RAG) using LangChain, ChromaDB, and the Anthropic Claude API. This project explores different approaches to building RAG systems, from simple text-based implementations to advanced document management with persistent vector storage.

## Features

- **Multiple RAG Implementations**: Progressive examples from basic text RAG to advanced vector store management
- **PDF Document Processing**: Load and process PDF documents for RAG queries
- **Local Vector Storage**: Persistent vector database using ChromaDB for efficient document retrieval
- **Dynamic Document Addition**: Add new documents to existing vector stores without rebuilding
- **LangChain Integration**: Leverages LangChain for seamless LLM and retrieval chain management
- **Jupyter Notebooks**: Interactive notebooks for experimentation and learning
- **Environment Configuration**: Secure management of API keys and configuration

## Project Structure

```
RAG_POC/
├── 1.0_RAG_With_Own_Text.ipynb      # Basic RAG implementation with custom text
├── 2.0_RAG_With_PDF.ipynb            # RAG using PDF documents
├── 3.0_RAG_Store_in_Local_store.ipynb # RAG with persistent local vector store
├── 4.0_RAG_Add_Docu.ipynb            # RAG with dynamic document addition
├── VectorDB/                         # Local ChromaDB vector database storage
├── Docs/                             # Sample PDF documents for RAG
├── requirements.txt                  # Python package dependencies
├── pyproject.toml                    # Project configuration
├── .env                              # Environment variables (not included in repo)
└── README.md                         # This file
```

## Tech Stack

- **Python** - Core programming language
- **LangChain** - LLM application framework
- **ChromaDB** - Vector database for document embeddings
- **Jupyter Notebooks** - Interactive computing environment
- **Anthropic Claude API** - Large language model API

## Installation

### Prerequisites

- Python 3.8 or higher
- pip (Python package installer)
- An Anthropic API key

### Steps

1. **Clone the repository**
   ```bash
   git clone https://github.com/debnathAiincorg/RAG_POC.git
   cd RAG_POC
   ```

2. **Create a virtual environment** (recommended)
   ```bash
   python -m venv venv
   ```

3. **Activate the virtual environment**
   - On Windows:
     ```bash
     venv\Scripts\activate
     ```
   - On macOS/Linux:
     ```bash
     source venv/bin/activate
     ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Configuration

### Environment Variables

Create a `.env` file in the project root directory with the following configuration:

```
ANTHROPIC_API_KEY=your_api_key_here
```

To obtain your Anthropic API key:
1. Visit [https://console.anthropic.com](https://console.anthropic.com)
2. Sign up or log in to your account
3. Navigate to the API keys section
4. Generate a new API key
5. Copy the key and paste it into your `.env` file

**⚠️ Important**: Never commit the `.env` file to version control. Ensure it's listed in `.gitignore`.

## Usage

Each notebook in the project demonstrates a different aspect of RAG systems. Run them in order for a progressive learning experience.

### 1. Basic RAG with Custom Text
```
1.0_RAG_With_Own_Text.ipynb
```
This notebook demonstrates the fundamentals of RAG using simple custom text data. Ideal for understanding the core concepts.

### 2. RAG with PDF Documents
```
2.0_RAG_With_PDF.ipynb
```
Learn how to load and process PDF documents and use them as context for RAG queries. Includes examples of working with the sample documents in the `Docs/` directory.

### 3. RAG with Local Vector Store
```
3.0_RAG_Store_in_Local_store.ipynb
```
Explore persistent vector storage using ChromaDB. This notebook shows how to store embeddings locally for reuse across sessions, improving performance and reducing API calls.

### 4. Adding Documents to Vector Store
```
4.0_RAG_Add_Docu.ipynb
```
Advanced usage: dynamically add new documents to an existing vector store without rebuilding it from scratch.

### Running a Notebook

1. Launch Jupyter Notebook:
   ```bash
   jupyter notebook
   ```

2. Navigate to the desired notebook and click to open it

3. Execute cells in sequence using `Shift + Enter` or the "Run" button

4. Ensure your `.env` file is properly configured before running cells that interact with the Anthropic API

## Requirements

See `requirements.txt` for the complete list of dependencies. Key packages include:

- `langchain` - LLM application framework
- `chromadb` - Vector database
- `python-dotenv` - Environment variable management
- `jupyter` - Interactive notebook environment
- `anthropic` - Anthropic API client
- `pypdf` - PDF document processing

To view all dependencies:
```bash
cat requirements.txt
```

## Project Configuration

Additional project settings are configured in `pyproject.toml`. This file includes metadata about the project, build configurations, and tool-specific settings.

## Vector Database

The `VectorDB/` directory contains the local ChromaDB vector database. This directory is automatically created and managed by the notebooks. It stores document embeddings for efficient retrieval.

**Note**: This directory may be large depending on the number of documents processed. You can regenerate it by running the relevant notebooks.

## Sample Documents

The `Docs/` directory contains sample PDF documents used in the RAG examples. You can:
- Add your own PDF files to this directory
- Modify notebook paths to use your custom documents
- Process documents using notebook 2.0 and beyond

## Troubleshooting

### API Key Issues
- Ensure your `.env` file contains the correct `ANTHROPIC_API_KEY`
- Verify the API key is active in your Anthropic console
- Check that your API key has sufficient credits

### Module Import Errors
- Ensure all dependencies are installed: `pip install -r requirements.txt`
- Verify you're using the correct Python virtual environment
- Clear pip cache if needed: `pip install --upgrade --force-reinstall -r requirements.txt`

### ChromaDB Issues
- The `VectorDB/` directory is automatically created; ensure write permissions exist
- Delete the `VectorDB/` directory to reset the vector database
- Run the setup cells in the notebooks to reinitialize

## Learning Resources

- [LangChain Documentation](https://python.langchain.com)
- [ChromaDB Documentation](https://docs.trychroma.com)
- [Anthropic API Documentation](https://docs.anthropic.com)
- [RAG Concepts Guide](https://docs.anthropic.com/en/docs/build-a-chatbot)

## License

This project is provided as-is for educational and proof-of-concept purposes.

## Author

Created by debnathAiincorg

---

**Note**: This is a proof of concept. For production use, consider implementing additional features such as:
- Error handling and logging
- Input validation and sanitization
- Performance optimization for large datasets
- Security hardening for API interactions
- Comprehensive unit and integration tests
