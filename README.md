
---

## 📚 Retrieval-Augmented Generation (RAG) with Mistral 7B Instruct

This repository demonstrates how to build a **fully local RAG pipeline** using open-source models — with no reliance on OpenAI or closed APIs.

> 🔍 Ask questions based on your own documents — PDFs, text files, datasets — and get accurate, source-grounded answers using `Mistral-7B-Instruct-v0.2`.

---

### 🚀 Features

* ✅ End-to-End RAG implementation
* 🧠 LLM: [Mistral 7B Instruct](https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.2)
* 🔎 Fast retrieval using FAISS vector search
* 🧱 Chunking, Embeddings, and Prompt Engineering with LangChain
* 🔒 100% Local — No cloud, No OpenAI key needed
* 📁 Load data from TXT, Markdown, or JSONL (expandable to PDF/CSV)

---

### 🛠️ Tech Stack

* `LangChain`
* `transformers` (HuggingFace)
* `sentence-transformers`
* `FAISS`
* `datasets`
* `bitsandbytes` (for 4-bit quantization)

---

### 📦 Installation

```bash
git clone https://github.com/yourusername/rag-mistral7b.git
cd rag-mistral7b

# Install dependencies
pip install -r requirements.txt

# Optional: Use virtualenv
python -m venv venv
source venv/bin/activate
```

---

### 🔧 Usage

#### 1. **Set HuggingFace Token (for gated model)**

```bash
huggingface-cli login
```

Make sure you have accepted access to [`Mistral-7B-Instruct-v0.2`](https://huggingface.co/mistralai/Mistral-7B-Instruct-v0.2).

#### 2. **Prepare your data**

Place your documents inside the `data/` folder (e.g., `.txt`, `.md`, `.jsonl`)

#### 3. **Run the pipeline**

```bash
python main.py
```

This will:

* Load & split your documents into chunks
* Embed them with `sentence-transformers`
* Store them in a FAISS index
* Accept a user query
* Retrieve relevant chunks and generate an answer using Mistral 7B

---

### 🧠 Architecture Overview

```text
[Documents] → [Chunking] → [Embedding] → [FAISS Vector DB]
                                  ↑
                                  ↓
                            [Retriever]
                                  ↑
                            [Query Input]
                                  ↓
                    [RAG Prompt + Mistral 7B Output]
```

---

### 📝 Example Output

**Input:**

> "What is the refund policy of the company?"

**Output:**

> "The company offers a 30-day refund policy. If you're not satisfied, you can request a refund within that period."

---

### ✅ Future Improvements

* Add support for PDF, CSV, and Word documents
* Serve via API (FastAPI) or Chatbot UI
* Add streaming support and memory for conversations
* Switch between different embedding models

---

### 🙌 Acknowledgements

* [Mistral AI](https://huggingface.co/mistralai)
* [LangChain](https://github.com/langchain-ai/langchain)
* [HuggingFace Transformers](https://huggingface.co/docs/transformers/index)
* [FAISS](https://github.com/facebookresearch/faiss)

---

### 📄 License

MIT License. Feel free to use and modify.

---
