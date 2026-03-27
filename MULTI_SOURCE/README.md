
# Intelligent Multi-Source Research Assistant (Advanced RAG)

## Overview
This project implements an AI-powered assistant that answers user queries by retrieving and synthesizing information from multiple data sources:

1. PDF (technical documentation)
2. CSV/JSON (structured data)
3. Markdown (unstructured text)

It uses a Retrieval-Augmented Generation (RAG) pipeline with an intelligent agent that selects the right tool based on query intent.

## Features
### Data Ingestion
- Supports PDF, CSV, and Markdown files
- Automatically:
  - Loads documents
  - Cleans and preprocesses data
  - Splits into chunks
  - Generates embeddings

### Knowledge Base (RAG)
- Uses Chroma Vector Database
- Embeddings generated via:
  - `sentence-transformers/all-MiniLM-L6-v2`
- Retrieves top relevant chunks for answering queries

## Intelligent Agent System
1. **Factual Q&A Tool**
   - Answers direct questions
   - Retrieves top relevant chunks
2. **Comparative Analysis Tool**
   - Compares data across sources
   - Extracts metrics (accuracy, precision, recall)
   - Can generate structured tables
3. **Summarization Tool**
   - Produces topic-level or document-level summaries

## Agent Dispatcher
- Automatically classifies user query into:
  - `factual`
  - `comparative`
  - `summary`
- Routes query to the correct tool

## Answer Attribution
Each response includes:
- Source filenames
- Chunk-level context
- Confidence score (High / Medium / Low)

## User Interface 
Built using Gradio:
- Upload multiple files 
- Enter query 
- View:
  - Answer 
  - Tool used 
  - Sources 
  - Confidence score 

## How It Works
1. Upload files (PDF, CSV, Markdown)
2. Documents are:
   - Split into chunks  Converted into embeddings Stored in vector database (Chroma) User enters query Agent: Classifies intent Selects tool Relevant chunks retrieved LLM generates final answer with citations.

## Installation 
```bash
pip install langchain langchain-community langchain-openai
pip install chromadb sentence-transformers
pip install pypdf pandas gradio rank_bm25```
