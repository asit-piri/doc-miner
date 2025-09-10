# Medical Document Chatbot

This project provides a Streamlit-based chatbot for uploading, processing, and querying medical documents. It integrates **ChromaDB** for vector storage, **OpenAI/Euri APIs** for embeddings and LLM responses, and optional **AWS S3** and **emailing features** for workflow automation.

---

## Overview

The Medical Document Chatbot allows researchers, doctors, and students to:
- Upload and parse medical PDFs
- Store embeddings in **ChromaDB**
- Chat with an AI assistant using document context
- Automate workflows with **S3 integration** and **email reports**
- Save and reload chat sessions for continuity

---

## Workflow

### Distribution of Features:
- **40% (Document Upload & Parsing)**: Upload PDFs and extract text with `pypdf`  
- **30% (Vector Storage)**: Store embeddings in **ChromaDB** for retrieval  
- **15% (Chat & QA)**: Query documents through the chatbot interface  
- **10% (Cloud Integration)**: Fetch and process files directly from **AWS S3**  
- **5% (Utilities)**: Email reports, clear DB, create support tickets  

---

## File Structure

```

Doc-Miner/
├── app/ # Core application logic
│ ├── init.py
│ ├── chat_utils.py # Chat & LLM query handling
│ ├── config.py # App configuration
│ ├── email_utils.py # Email integration
│ ├── pdf_utils.py # PDF text extraction
│ ├── s3_utils.py # AWS S3 helpers
│ ├── ui.py # Streamlit UI components
│ └── vectorstore_utils.py # ChromaDB vector store logic
│
├── .dockerignore # Ignore files for Docker build
├── .env # Environment variables
├── .gitignore # Git ignore rules
├── apprunner.yaml # AWS App Runner config
├── deploy-to-ecr.bat # Windows deploy script
├── deploy-to-ecr.sh # Linux/macOS deploy script
├── Dockerfile # Docker build instructions
├── main.py # Streamlit entrypoint
├── requirements.txt # Python dependencies
└── test.ipynb # Jupyter notebook for testing

```
---
## Usage
Run the app:
'''
streamlit run app.py
'''
### In the app:

- Upload PDF medical documents → they are parsed and added to ChromaDB.

- Ask questions in the chat box → chatbot retrieves relevant chunks and answers.

- Use sidebar options:

-- Clear documents from DB

-- Save session

-- Send test email

-- Process S3 documents

-- Create support ticket

---

## Requirements
'''
Key libraries:
'''
'''
streamlit
'''
'''
pypdf
'''
'''
chromadb
'''
'''
langchain
'''
'''
sentence-transformers
'''
'''
boto3
'''
'''
openai
'''
'''
fpdf2
'''
'''
python-dotenv
'''
See requirements.txt for exact pinned versions.

---

## Notes

- ChromaDB is run locally using **PersistentClient**.

- For OpenAI/Euri usage, make sure to set correct environment variables.

- Uploaded PDFs are split into text chunks before embedding.

- Session data is stored locally and can be exported.

- Emailing requires a valid SMTP setup (configured in **email_utils.py**).
