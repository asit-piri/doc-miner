# Doc-Miner - Intelligent Document Assistant

Doc Miner is an advanced AI-powered application designed to assist with multi-modal document analysis and intelligent chat interactions. It leverages large language models, document processing, and vector storage to provide insightful responses to user queries.

## Features

- PDF document upload and processing
- S3 integration for document storage
- ChromaDB for efficient vector storage and retrieval
- Intelligent chat interface powered by self-hosted language models in cloud
- Document Analytics and Insights generation
- Email reporting functionality
- Support ticket creation

## Technologies Used

- Python 3.11
- Streamlit for the web interface
- OpenAI API for language model interactions
- ChromaDB for vector storage
- AWS S3 for document storage
- Docker for containerization
- Various Python libraries including langchain, sentence-transformers, and more

## Setup and Installation

1. Clone the repository
2. Install dependencies:

---

## Usage
- Upload documents through the Streamlit interface.
- Ask questions about the uploaded documents using natural language.
- Receive AI-generated responses based on the document content.
- Send analysis reports or create support tickets as needed.

## Deployment

The project includes deployment scripts for AWS ECR and App Runner:

- For Unix-based systems: deploy_ecr.sh
- For Windows: deploy_ecr.bat
- Follow the instructions in these scripts to deploy the application to AWS.

---

## Overview

The Doc Miner Chatbot allows researchers, layers, doctors, government agencies and students to:
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
```
streamlit run app.py
```
### In the app:

- Upload PDF medical documents → they are parsed and added to ChromaDB.

- Ask questions in the chat box → chatbot retrieves relevant chunks and answers.

Use the sidebar options:

- Clear documents from DB

- Save session

- Send test email

- Process S3 documents

- Create support ticket

---

## Requirements

Key libraries:

```
streamlit
```
```
pypdf
```
```
chromadb
```
```
langchain
```
```
sentence-transformers
```
```
boto3
```
```
openai
```
```
fpdf2
```
```
python-dotenv
```
See **requirements.txt** for exact pinned versions.

---


## Deployment

The application can be deployed using Docker. Use the provided `Dockerfile` and deployment scripts:

- For Unix-based systems: `deploy_ecr.sh`
- For Windows: `deploy_ecr.bat`

These scripts build the Docker image and push it to Amazon ECR for deployment.

## Usage

1. Upload medical documents (PDFs) using the sidebar
2. Process the documents to store them in S3 and create vector embeddings
3. Use the chat interface to ask questions about the medical documents
4. Utilize additional features like email reporting and support ticket creation

## Contributing

Contributions to MediChat Pro are welcome. Please ensure to follow the coding standards and submit pull requests for any new features or bug fixes.

## License

[Specify your license here]

## Support

For any issues or questions, please create a support ticket using the in-app feature or contact the development team.

## Notes

- ChromaDB is run locally using **PersistentClient**.

- For OpenAI/Euri usage, make sure to set correct environment variables.

- Uploaded PDFs are split into text chunks before embedding.

- Session data is stored locally and can be exported.

- Emailing requires a valid SMTP setup (configured in **email_utils.py**).
