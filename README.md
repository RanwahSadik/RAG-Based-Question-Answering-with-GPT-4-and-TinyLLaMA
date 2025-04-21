# RAG-Based Question Answering with GPT-4 and TinyLLaMA


## 📌 Overview

This project implements a **Retrieval-Augmented Generation (RAG)** pipeline to extract insights from academic PDFs using both **OpenAI's GPT-4** and **TinyLLaMA** models. It enables users to upload research papers and ask questions interactively, with answers grounded in document content.

---

## 🧠 Key Features

- 🔍 Extracts and processes full-text PDFs
- 📚 Embeds content using either **OpenAI** or **Sentence Transformers**
- 📦 Stores knowledge in a **FAISS** vector database
- 🔄 Two working pipelines:
  - `GPT-4 + OpenAI Embeddings`
  - `TinyLLaMA + SentenceTransformer Embeddings`
- ❓ Answers both direct and indirect questions using document context

---

## 🧠 How It Works

### 1. **PDF Extraction and Chunking**

The project begins by loading and processing a PDF document, splitting it into manageable chunks. This ensures that large documents are handled efficiently, making the system capable of precise retrieval when querying.

### 2. **Embedding and FAISS Indexing**

Once the document is split, the content is embedded using one of the available embedding methods (either OpenAI's embeddings for GPT-4 or SentenceTransformers for TinyLLaMA). These embeddings are then stored in a **FAISS index**, which allows for fast retrieval during question answering.

### 3. **Retrieval-Augmented Generation (RAG)**

Using the stored embeddings, the system performs **Retrieval-Augmented Generation (RAG)**. It retrieves relevant document chunks for a given query and generates an answer using the selected model (either GPT-4 or TinyLLaMA). This approach ensures that answers are grounded in the content of the document, providing accurate responses.

---
## ⚖️ Model Comparison: GPT-4 vs. TinyLLaMA

| Feature                        | **GPT-4 (OpenAI)**                      | **TinyLLaMA (LLaMA.cpp)**                   |
|-------------------------------|-------------------------------------------|-----------------------------------------------|
| **Model Size**                | 175B (accessed via cloud API)             | 1.1B (runs locally using GGUF file)            |
| **Embedding Method**          | `OpenAIEmbeddings`                        | `all-MiniLM-L6-v2` (SentenceTransformer)       |
| **Indirect Question Handling**| ✅ Excellent context understanding         | ⚠️ Limited, struggles with non-explicit prompts|
| **Ease of Setup**             | ✅ Easy, no infrastructure required        | 🛠 Requires local setup & model download        |
| **Performance**               | High accuracy and fluency                 | Lightweight, faster inference on small docs    |
| **Cost**                      | 💰 Paid (OpenAI token usage applies)       | 🆓 Free, once downloaded                       |
| **Inference Speed**           | ⚡ Fast (API optimized)                    | ⚡ Fast (after initial load, efficient on CPU)  |


---

### 📝 Summary

- ✅ **GPT-4 outperforms** in terms of **contextual accuracy, indirect question handling, and fluency** of answers.
- 🔄 **TinyLLaMA is ideal** for **offline use**, fast prototyping.
- 
---
  ## 📚 References

- [A Recommender System for Healthy Food Choices: Building a Hybrid Model for Recipe Recommendations Using Big Data Sets](https://www.researchgate.net/publication/349152789_A_Recommender_System_for_Healthy_Food_Choices_Building_a_Hybrid_Model_for_Recipe_Recommendations_using_Big_Data_Sets)
