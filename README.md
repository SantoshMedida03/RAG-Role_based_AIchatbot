 📌 Overview

This project is a Role-Based AI Chatbot designed for organizations to securely query internal documents using Retrieval-Augmented Generation (RAG). Each department such as HR, Finance, Marketing, Engineering, and General can access only their own documents, ensuring strict data isolation, privacy, and security.

The system uses LangChain for orchestration, ChromaDB for vector storage, and Ollama running LLaMA 3.1 locally as the Large Language Model (LLM). All AI inference happens locally on the machine, eliminating dependency on cloud APIs and preventing sensitive data from leaving the system.

🎯 Key Features

🔐 Role-Based Access Control (RBAC) – Department-wise document isolation

📚 RAG Architecture – Accurate answers using retrieval + generation

🧠 Local LLM with Ollama – No cloud dependency, complete data privacy

🗂️ Department-wise Document Organization – HR, Finance, Marketing, Engineering, General

⚡ Fast Vector Search – Powered by ChromaDB

📄 Supports Unstructured & Structured Data – Markdown and CSV files

🏢 Enterprise-Ready Design – Secure and scalable architecture

🛠️ Tech Stack

Language: Python

Backend: FastAPI

Frontend: Streamlit

RAG Framework: LangChain

Vector Database: ChromaDB

LLM Runtime: Ollama (LLaMA 3.1)

Data Formats: Markdown, CSV

🏗️ System Architecture
User
  ↓
Streamlit Frontend
  ↓
FastAPI Backend
  ↓
LangChain (RAG Pipeline)
  ↓
ChromaDB (Vector Search + Role Filtering)
  ↓
Ollama (Local LLaMA 3.1)
  ↓
AI Response

🔄 How It Works

Documents are stored department-wise inside the resources/data/ directory

All documents are embedded and indexed into ChromaDB using LangChain

User selects their role and enters a query

System retrieves only documents permitted for that role

Retrieved context is sent to Ollama (LLaMA 3.1) for answer generation

AI returns a secure, role-filtered response

📁 Project Structure
role_based_aichatbot/
│
├── app/
│   ├── main.py
│   ├── frontend.py
│   ├── embed_documents.py
│   └── chroma_store/
│
├── resources/
│   └── data/
│       ├── hr/
│       ├── finance/
│       ├── marketing/
│       ├── engineering/
│       └── general/
│
├── requirements.txt
├── pyproject.toml
└── README.md

⚙️ Setup & Installation
1️⃣ Clone the repository
git clone https://github.com/SantoshMedida03/RAG-Role_based_AIchatbot.git
cd RAG-Role_based_AIchatbot

2️⃣ Create virtual environment
python -m venv venv
venv\Scripts\activate   # On Windows

3️⃣ Install dependencies
pip install -r requirements.txt

🧠 Setup Ollama (Local LLM)

Install Ollama from: https://ollama.com

Start Ollama and pull LLaMA 3.1 model:

ollama run llama3.1


Keep this running in a separate terminal.

📥 Embed Documents (Important Step)

Before running the chatbot, you must embed all documents:

cd app
python embed_documents.py


This will:

Read documents from resources/data/

Generate embeddings

Store them in ChromaDB

▶️ Run the Application
Start Backend
python main.py

Start Frontend
streamlit run frontend.py


Now open the browser and start chatting 🚀

🔐 Security & Privacy

All processing is local

No data is sent to external APIs

Role-based filtering is enforced at the retrieval layer

Prevents cross-department data access

💡 Use Cases

Internal company knowledge assistant

Secure HR/Finance/Engineering chatbot

Enterprise AI assistant

Privacy-first AI applications

🧠 Why This Project?

This project demonstrates:

Real-world RAG implementation

Role-based system design

Local LLM deployment using Ollama

Enterprise-level security awareness

Practical GenAI engineering skills

📌 One-Line Summary

A secure, role-based RAG AI chatbot using LangChain, ChromaDB, and Ollama (LLaMA 3.1) for private enterprise document querying.

⭐ Author

Santosh Medida
B.Tech CSE (2026) | AI/ML & GenAI Enthusiast
GitHub: https://github.com/santoshmedida03

🙌 Acknowledgements

LangChain

ChromaDB

Ollama

Meta AI (LLaMA 3.1)
