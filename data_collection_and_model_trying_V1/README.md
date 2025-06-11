# 🧠 RAG System for Customer Service  
*A system designed to handle customer queries using the company's knowledge base with LLaMA 3, LangChain, and local embeddings.*

---

## 📂 Project Notebooks

### 📘 `web_scrapping_KB.ipynb`
- **Purpose:** Scrapes the HTML structure of the company's knowledge base page.
- **Functionality:**
  - Identifies and extracts sections containing **FAQ** and **article links**.
  - Fetches the content of these nested links.
  - Saves the data for future processing (e.g., embedding, retrieval).
- **Next Step:** Ensure recursive or sitemap-based extraction for comprehensive coverage.

---

### 🧪 `KnowledgeBase_llama_rag_v1.ipynb`
- **Purpose:** Contains the first working trial of the Retrieval-Augmented Generation (RAG) pipeline.
- **Key Features:**
  - Integrates **LLaMA 3** for invocation and **nomic-embed-text** for embedding.
  - Utilizes LangChain to handle question-answering.
- **Current Status:** Produces good initial results.
- **Improvement Areas:**
  - Enhance context relevance.
  - Improve long-form answers and multi-turn understanding.

---

## 🎥 Tutorial

### 🔗 [Build an AI Chatbot with Local RAG + LangChain + Ollama](https://www.youtube.com/watch?v=fk8AeppfnTg)
[![YouTube Tutorial](https://img.youtube.com/vi/fk8AeppfnTg/0.jpg)](https://www.youtube.com/watch?v=fk8AeppfnTg)

---

Let me know if you want to generate a README.md for the entire project, or if you'd like to include architecture diagrams or code blocks inside this Markdown.
