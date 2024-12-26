# PDF Chat Assistant

## Overview
The PDF Chat Assistant is a full-stack application designed to process PDF documents and enable users to ask questions about their content. The backend leverages FastAPI for API development and integrates a custom PDF processing pipeline. The frontend is built using Streamlit for an interactive and user-friendly experience.

---

## Features

1. **User Authentication**:
   - Registration and login functionalities with email and password.

2. **PDF Upload**:
   - Supports uploading multiple PDFs for processing.

3. **PDF Text Extraction**:
   - Extracts text and metadata from PDFs using PyPDF2 and OCR for image-based content.

4. **Vector Database Storage**:
   - Stores processed text as vectors in Qdrant for efficient similarity search.

5. **Question Answering**:
   - Provides answers to user queries based on the processed PDF content using LangChain.

6. **Frontend Application**:
   - Simple and intuitive user interface with login, registration, document management, and question-answering capabilities.

---

## Technology Stack

### Backend:
- **FastAPI**: API development.
- **SQLite**: Database for user data.
- **LangChain**: Text processing and question-answering.
- **Qdrant**: Vector storage for similarity search.
- **PyPDF2** and **Tesseract OCR**: Text extraction from PDFs.

### Frontend:
- **Streamlit**: Web interface.

### Additional Tools:
- **Google Generative AI**: For conversational AI capabilities.
- **HuggingFace Embeddings**: For embedding PDF content.

---

## Prerequisites

- Python 3.8+
- Tesseract OCR
- SQLite (pre-installed on most systems)

### Environment Variables
Create a `.env` file with the following variables:
```
GOOGLE_API_KEY=<Your Google Generative AI API Key>
QDRANT_URL=<Your Qdrant URL>
QDRANT_API_KEY=<Your Qdrant API Key>
DB_PATH=chat_app.db
```

---

## Installation

1. Clone the repository:
   ```bash
   git clone <repository-url>
   cd <repository-directory>
   ```

2. Create a virtual environment:
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows, use `venv\Scripts\activate`
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Install Tesseract OCR (if not installed):
   ```bash
   sudo apt install tesseract-ocr  # For Ubuntu
   brew install tesseract          # For macOS
   ```

---

## Running the Application

### Backend:
1. Navigate to the `api` directory:
   ```bash
   cd api
   ```

2. Start the FastAPI server:
   ```bash
   uvicorn app:app --host 0.0.0.0 --port 8000 --reload
   ```

### Frontend:
1. Navigate to the `frontend` directory:
   ```bash
   cd frontend
   ```

2. Start the Streamlit app:
   ```bash
   streamlit run app.py
   ```

---

## API Endpoints

### Authentication:
- **POST /register**:
  Register a new user.

### PDF Processing:
- **POST /upload-pdfs**:
  Upload and process PDF files.

### Question Answering:
- **POST /ask**:
  Ask a question about the processed PDFs.

---

## Usage

1. Open the Streamlit frontend in your browser (default: `http://localhost:8501`).
2. Create an account or log in.
3. Upload PDFs and process them.
4. Ask questions about the uploaded documents and receive answers.

---

## Development Notes

### Directory Structure
```
project/
|-- api/
|   |-- app.py                # FastAPI application
|   |-- database.py           # Database setup and operations
|   |-- pdf_processor.py      # PDF processing logic
|   |-- models.py             # Pydantic models for request/response
|-- frontend/
|   |-- app.py                # Streamlit application
|-- .env                      # Environment variables
|-- requirements.txt          # Python dependencies
```



