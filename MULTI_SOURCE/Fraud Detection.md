\# Fraud Detection AI Assistant Project

\#\# Project Overview  
This project implements an AI-powered knowledge assistant for a fraud detection system. The assistant can answer questions, perform comparative analyses, and generate summaries by pulling information from multiple data sources including:

\- \*\*PDF documentation\*\* (\`manual.pdf\`) describing models, metrics, and system usage.  
\- \*\*CSV dataset\*\* (\`transactions.csv\`) containing historical transaction data.  
\- \*\*Markdown notes\*\* (\`readme.md\`) for project overview, usage instructions, and explanations.

The goal is to provide an intelligent system that can retrieve accurate answers, cite sources, and provide confidence scores for all responses.

\---

\#\# Dataset  
The main dataset for this project is \`transactions.csv\`. Key points:

\- \*\*Features\*\*:   
  \- \`transaction\_id\` (unique identifier)    
  \- \`amount\` (transaction amount in USD)    
  \- \`merchant\` (merchant name)    
  \- \`user\_id\` (unique user ID)    
  \- \`is\_fraud\` (1 \= fraudulent, 0 \= legitimate)  
\- \*\*Size\*\*: 100,000 transactions  
\- \*\*Notes\*\*:    
  \- Data is anonymized.    
  \- Used for training, testing, and validation of machine learning models.  

Example entries from the dataset:

| transaction\_id | amount  | merchant    | user\_id | is\_fraud |  
|----------------|---------|------------|---------|----------|  
| 1              | 250.50  | Amazon     | 101     | 0        |  
| 2              | 1200.00 | Walmart    | 102     | 1        |  
| 3              | 75.00   | Starbucks  | 103     | 0        |

\---

\#\# Machine Learning Models  
Three models are implemented and evaluated:

\#\#\# 1\. Random Forest Classifier  
\- Accuracy: 0.91    
\- Precision: 0.88    
\- Recall: 0.85    
\- Notes: Handles categorical features well and is robust to overfitting.  

\#\#\# 2\. XGBoost Classifier  
\- Accuracy: 0.94    
\- Precision: 0.91    
\- Recall: 0.89    
\- Notes: Highest performance overall, slightly slower to train.

\#\#\# 3\. Logistic Regression  
\- Accuracy: 0.86    
\- Precision: 0.83    
\- Recall: 0.80    
\- Notes: Simple baseline model, interpretable coefficients, fast inference.

\---

\#\# System Architecture  
The AI assistant is structured as follows:

1\. \*\*Data Ingestion\*\*: Upload files (PDF, CSV, Markdown).    
2\. \*\*Preprocessing\*\*: Clean, chunk, and create embeddings.    
3\. \*\*Vector Store\*\*: Embeddings stored in Chroma for fast retrieval.    
4\. \*\*Agent Dispatcher\*\*: Classifies query type:  
   \- \*\*Factual Q\&A\*\* → retrieves specific information  
   \- \*\*Comparative / Analytical\*\* → compares metrics across sources  
   \- \*\*Summary\*\* → generates document-level or topic-level summaries    
5\. \*\*Response Generation\*\*: Uses LLM to synthesize answer with:  
   \- Source citations  
   \- Confidence score (high / medium / low)

\---

\#\# Example Queries  
\- “Which model has the highest accuracy?”    
\- “Compare accuracy, precision, and recall for all models.”    
\- “Summarize the dataset and model usage instructions.”    
\- “List steps to preprocess new transaction data.”

\---

\#\# Usage Instructions  
1\. Upload the \`manual.pdf\`, \`transactions.csv\`, and \`readme.md\` files.    
2\. Enter a question in the AI assistant UI.    
3\. The assistant retrieves relevant information, generates an answer, cites sources, and displays a confidence score.  

\---

\#\# Recommendations  
\- XGBoost is recommended for high accuracy requirements.    
\- Random Forest is a good balance between speed and precision.    
\- Logistic Regression can serve as a baseline or backup.    
\- Regularly retrain models with new transaction data for consistent performance.

\---

\#\# References  
\- \`manual.pdf\` → Technical documentation    
\- \`transactions.csv\` → Structured dataset    
\- \`readme.md\` → Project overview and usage  
