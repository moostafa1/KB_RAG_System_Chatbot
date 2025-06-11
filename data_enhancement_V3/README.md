# 🧹 Knowledge Base Preprocessing Pipeline

This repository provides a Python-based data preprocessing pipeline tailored for preparing knowledge base articles to be used in a **Retrieval-Augmented Generation (RAG)** system. It cleans raw HTML content, extracts metadata, splits content into chunks, and enriches each chunk with relevant metadata for downstream use in embedding and retrieval.

---

## 📦 Features

### ✅ Metadata Handling
- Automatically identifies and adds the `type` of each article: `FAQ` or `Tutorial`.
- Extracts and stores embedded URLs as `references` in the metadata.
- Cleans and unescapes HTML-encoded `title` values.

### ✅ Content Cleaning
- Strips unwanted HTML tags and characters.
- Removes broken paths such as `clientarea.php`, `index.php`, `.exe`, `.zip`, etc.
- Normalizes whitespace, line breaks, and removes redundant promotional boilerplate.

### ✅ Link Handling
- Identifies full URLs in the document using regex.
- Replaces internal links with a placeholder (`[our client area link]`) to retain intent without exposing raw URLs.
- Removes external links from the text while saving them to the metadata.

### ✅ Chunking Strategy
- Splits documents based on step-by-step structures, headings, or newlines.
- Discards trivial chunks with fewer than 10 words.
- Preserves semantic structure by merging headings with their respective content.

### ✅ Tagging & Enrichment
- Tags each chunk based on domain-specific keywords (`linux`, `ssl`, `vps`, `docker`, etc.).
- Extracts CLI commands (`sudo`, `docker`, `apt-get`, `curl`) to assist in technical content classification.
- Assigns a unique UUID to each chunk for tracking and retrieval.

---

## 🧩 Main Components

| Function | Purpose |
|---------|---------|
| `clean_and_extract_urls()` | Extracts all URLs, classifies internal vs. external, updates metadata |
| `clean_document()` | Unescapes HTML titles and removes boilerplate |
| `split_into_chunks()` | Splits cleaned text into manageable chunks |
| `extract_commands()` | Pulls out command-line instructions for tagging |
| `tag_chunk()` | Adds relevant tags based on keyword presence |
| `preprocess_document()` | Integrates all steps to process one document |
| `preprocess_all()` | Processes a list of LangChain `Document` objects |

---

## 📄 Sample Output Schema

Each chunk output is a dictionary with the following structure:

```json
{
  "id": "uuid",
  "content": "Step 1: Access the control panel...",
  "source": "https://example.com/knowledgebase/article",
  "title": "How to Set Up SSL",
  "type": "Tutorial",
  "chunk_index": 0,
  "commands": ["sudo apt-get install openssl"],
  "tags": ["ssl", "linux"],
  "references": ["https://external-resource.com/help"]
}
