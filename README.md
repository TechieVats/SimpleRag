# Simple RAG System

A basic Retrieval Augmented Generation (RAG) system built with LangChain that allows you to ask questions about PDF documents.

## Features

- PDF document processing and text extraction
- Vector-based document search and retrieval
- Question answering with context from documents
- Support for both OpenAI and local Ollama models
- Streaming and batch processing capabilities

## Requirements

- Python 3.8+
- OpenAI API key (for OpenAI models)
- Ollama installation (for local models)

## Setup

1. Install required dependencies:
```bash
pip install langchain langchain-openai langchain-community python-dotenv pypdf docarray
```

2. For OpenAI models:
   - Create a `.env` file in the project root
   - Add your OpenAI API key: `OPENAI_API_KEY=your_api_key_here`

3. For local models:
   - Install Ollama from https://ollama.ai
   - Pull the required models:
   ```bash
   ollama pull mistral
   ollama pull nomic-embed-text
   ```

## Usage

1. Place your PDF document in the project directory
2. Open `notebook.ipynb` in Jupyter Notebook or JupyterLab
3. Update the MODEL variable to choose between:
   - OpenAI models: `"gpt-4o-mini"` or `"gpt-3.5-turbo"`
   - Local models: `"mistral:latest"` or other Ollama models
4. Run the cells sequentially to:
   - Load and process the PDF document
   - Create vector embeddings
   - Ask questions about the document content

## Model Configuration

The system supports two types of models:

### OpenAI Models
- Requires API key in `.env` file
- Uses OpenAI embeddings for document vectorization
- Recommended models: `gpt-4o-mini`, `gpt-3.5-turbo`

### Local Models (Ollama)
- No API key required
- Uses local Ollama embeddings (`nomic-embed-text`)
- Requires Ollama installation and model downloads
- Example models: `mistral:latest`, `llama2:latest`

## File Structure

- `notebook.ipynb` - Main implementation notebook
- `ADNOC_AnnualReport.pdf` - Sample PDF document
- `.env` - Environment variables (create this file)
- `README.md` - This file

## Example Questions

The system can answer questions like:
- "What is the purpose of this document?"
- "What are the key findings?"
- "Which are the most profitable segments?"

## Notes

- The system will respond with "I don't know" if the answer cannot be found in the document
- For better results, ensure your questions are specific and related to the document content
- Local models may have slower response times but don't require internet connectivity
