<div align="center">

# 🩺 Medical Chatbot  
### Context-Aware Clinical Q&A System using RAG

</div>

---

## 📌 Project Summary
This project is a **Retrieval-Augmented Generation (RAG) based medical chatbot** that answers user queries using a **trusted medical knowledge base (PDFs)** instead of relying only on LLM memory.

The system retrieves relevant medical content using **FAISS vector search** and generates accurate, context-grounded responses using **LLMs (Groq / HuggingFace)**.

The goal is to **reduce hallucination in AI responses** and improve reliability in sensitive domains like healthcare.

---

## 🎯 Key Highlights
- Built an **end-to-end RAG pipeline**
- Integrated **LLM + Vector Database (FAISS)**
- Ensured **context-based answer generation**
- Implemented **source traceability**
- Developed both **CLI and Web UI (Streamlit)**
- Modular and scalable code structure

---

## 🧠 How It Works

1. Load medical PDFs  
2. Split text into smaller chunks  
3. Convert chunks into embeddings  
4. Store embeddings in FAISS  
5. On user query:
   - Retrieve top relevant chunks  
   - Pass them to LLM as context  
6. Generate final answer with references  


---

## ⚙️ Tech Stack

**Languages & Frameworks**
- Python  
- Streamlit  

**AI / ML**
- Retrieval-Augmented Generation (RAG)  
- Sentence Transformers (`all-MiniLM-L6-v2`)  
- FAISS (Vector Database)  

**LLM Integration**
- Groq (Llama models)  
- HuggingFace Inference API  

**Libraries**
- LangChain  
- PyPDFLoader  
- FAISS  
- python-dotenv  

---

## 📁 Project Structure
medical-chatbot/
│── data/ # Medical PDFs
│── vectorstore/db_faiss # Stored FAISS index
│
├── create_memory_for_llm.py # Builds vector database
├── connect_memory_with_llm.py # CLI chatbot
├── medibot.py # Streamlit UI chatbot
├── requirements.txt
└── README.md

## 🗂️ Build Vector Database

Run once:
python create_memory_for_llm.py

This will:

Load PDFs
Split into chunks
Generate embeddings
Store them in FAISS

## 💬 Run the Application
▶ CLI Version
python connect_memory_with_llm.py
🌐 Web Version
streamlit run medibot.py
Open in browser: http://localhost:8501

## 📊 Key Functionalities
Accepts natural language medical queries
Retrieves relevant context using semantic search
Generates accurate answers using LLM
Displays supporting source content
Works via CLI and web interface

| Problem               | Solution                     |
| --------------------- | ---------------------------- |
| FAISS index not found | Run memory script first      |
| API key error         | Check `.env` file            |
| Low-quality answers   | Increase `k` value           |
| Environment issues    | Recreate virtual environment |

## 🔮 Future Improvements
Chat history support
Multi-document ingestion
UI/UX enhancements
Streaming responses
Multi-model support (OpenAI, Anthropic, etc.)

⚠️ Disclaimer
This project is for educational purposes only and does not provide medical advice.
---

## 🏗️ System Flow
