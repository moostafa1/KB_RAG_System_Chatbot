## 🔍 Observation on the Model's Behavior Using LLaMA 3

While testing the model notebook with the **LLaMA 3** model for both **invoking** and **embedding** data, an issue was noted regarding data scraping from websites.

### ⚠️ Limitation:
The current implementation scrapes **only the content of the main page** from the provided URL and does **not follow nested links** such as FAQs or Tutorials.

### 📎 Example:
When using the following URL for data scraping:  
`https://clients.hostsailor.com/index.php?rp=/knowledgebase`

The model fetches and processes content **only from the main knowledgebase page**, but **ignores**:
- Linked FAQ pages  
- Tutorial subpages  
- Any nested or related articles

### 💡 Recommendation:
For comprehensive knowledge base ingestion, consider:
- Implementing a **crawler** that traverses all nested links.
- Using a sitemap or manual link enumeration.
- Extracting structured content via API (if available) instead of HTML scraping.
