# Intelligent Document Q&A Assistant (Agentic RAG)

## Overview

This project is an AI-powered Document Assistant that allows users to:

- Upload a PDF document (10+ pages)
- Build a knowledge base using embeddings
- Ask questions about the document
- Get accurate answers with sources
- Generate full document summaries
- Download AI responses as a PDF

It uses a Retrieval-Augmented Generation (RAG) pipeline combined with an Agent-based routing system to intelligently decide how to respond.

## Key Features

1. **Document Ingestion**
   - Upload any PDF document
   - Extracts text from all pages
   - Splits into manageable chunks
   - Creates embeddings using SentenceTransformers

2. **Knowledge Base (Vector DB)**
   - Uses ChromaDB for storing embeddings
   - Retrieves most relevant chunks for Q&A

3. **Tools (LLM-powered)**
   - **Q&A Tool**
     - Answers specific questions
     - Uses retrieved document chunks
     - Provides source page references  
   - **Summarize Tool**
     - Generates a detailed summary of the entire document  
     - Structured output with headings & bullet points  

4. **Agent Dispatcher**
   - Classifies user query into:
     - `summarize`
     - `qa`
   - Routes request to correct tool automatically  

5. **User Interface (Gradio)**
   - Upload PDF  
   - Process document  
   - Ask questions  
   - View responses  
   - Download responses as PDF  

## Tech Stack
- LLM API: OpenRouter  
- Embeddings: SentenceTransformers (MiniLM)  
- Vector DB: ChromaDB  
- UI: Gradio  
- PDF Export: FPDF  

## Installation
```bash
pip install pypdf chromadb sentence-transformers gradio fpdf google-genai
```
