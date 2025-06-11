# 🧠 RAG System for Customer Service  
*A Retrieval-Augmented Generation (RAG) system that acts as a customer service representative by leveraging the company's knowledge base.*

---

### 🚀 `KnowledgeBase_llama_rag_v2.ipynb`

#### 🔄 Version 2 Enhancements:

- ✅ **Hyperlinked Sources**: Each source is displayed as a **clickable hyperlink**, showing the article `title` linked to the corresponding `article URL`.

- ✅ **Top 3 Results**: Retrieval configuration updated to fetch only the **top 3 most relevant documents** using:
  ```python
  vectorstore.as_retriever(search_kwargs={"k": 3})
