# How_Football_Began_RAG_Langchain - Please find Python Script in my drive - https://colab.research.google.com/drive/1Ds2m8NfIEIUfVrIz6rF9yVKtQCI68KpA?usp=sharing  , PDF file attached in the repository

🧠 RAG-Based Question Answering on Football History (LangChain + HuggingFace + FAISS)

This project demonstrates a Retrieval-Augmented Generation (RAG) pipeline built using LangChain, HuggingFace Transformers, and FAISS for vector search.
It loads a PDF document on the history of football, creates text embeddings, retrieves relevant chunks, and generates context-aware answers using a Flan-T5 model.
Finally, it evaluates system performance using RAGAS, ROUGE, BLEU, and BERTScore metrics.

🚀 Features

📄 PDF ingestion and preprocessing using PyPDFLoader

✂️ Recursive text chunking with RecursiveCharacterTextSplitter

🔍 FAISS-based vector search for efficient retrieval

🧩 Sentence-transformer embeddings (all-MiniLM-L6-v2)

🤖 Question answering via google/flan-t5-small LLM (HuggingFace pipeline)

📈 RAG Evaluation with:

context_precision

context_recall

faithfulness

answer_relevance

🧮 LLM Evaluation Metrics using evaluate:

ROUGE

BLEU

BERTScore

🧩 Tech Stack
Component	Library/Model
Document Loader	langchain_community.PyPDFLoader
Embeddings	sentence-transformers/all-MiniLM-L6-v2
Vector Store	FAISS
Language Model	google/flan-t5-small
Frameworks	LangChain, Transformers, Datasets, Evaluate, RAGAS
📚 Workflow Overview

Load and Clean the PDF

Load football history document.

Clean Unicode artifacts.

Chunk and Embed

Split into 500-character overlapping chunks.

Generate embeddings using HuggingFaceEmbeddings.

Build or Load FAISS Index

Persist local index for reuse.

Setup Retrieval-Augmented QA

Create RetrievalQA chain for contextual answers.

Ask Questions

Query the RAG pipeline interactively.

Evaluate Performance

Use RAGAS for retrieval metrics.

Use evaluate library for LLM generation quality.

🧠 RAGAS Evaluation
📊 RAGAS Evaluation Results:
context_precision: 0.742
context_recall: 0.685
faithfulness: 0.812
answer_relevance: 0.769

🔍 LLM Evaluation (Flan-T5)
ROUGE Scores:
  rouge1: 0.032
  rouge2: 0.000
  rougeL: 0.024
  rougeLsum: 0.024

BLEU Score: 0.000
BERTScore (F1): 0.347

🧪 Example Queries
Question	Generated Answer (Example)
When was the Football Association formed?	1863 in London
What is the main role of FIFA?	Governs international football competitions
Which country hosted the first FIFA World Cup?	Uruguay (1930)
How has technology changed football?	Use of VAR and goal-line systems
⚙️ Installation

Run in Google Colab or local Python environment:

!pip install -q langchain transformers sentence-transformers faiss-cpu huggingface_hub fpdf PyPDF2 accelerate --upgrade
!pip install -U ragas datasets evaluate rouge_score bert-score sacrebleu

🧠 Future Improvements

Upgrade to Flan-T5-XL or Mistral for higher accuracy

Integrate RAGAS v0.1.9+ for advanced metrics

Build a Streamlit UI for interactive querying

🏅 Author

Mulk Raj Dwivedi

💼 Data & ML Enthusiast | RAG, LangChain, and AI Systems Developer
