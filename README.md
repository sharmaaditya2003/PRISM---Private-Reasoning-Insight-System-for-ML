# PRISM 🔍
### Private Reasoning & Insight System for ML

> A privacy-preserving autonomous data science agent that runs entirely on-device — no cloud, no data leaks, no compromises.

![Python](https://img.shields.io/badge/Python-3.10+-blue?style=flat-square&logo=python)
![LangChain](https://img.shields.io/badge/LangChain-Enabled-green?style=flat-square)
![LangGraph](https://img.shields.io/badge/LangGraph-Multi--Node-orange?style=flat-square)
![Ollama](https://img.shields.io/badge/Ollama-Llama--3.2-purple?style=flat-square)
![Streamlit](https://img.shields.io/badge/UI-Streamlit-red?style=flat-square)
![License](https://img.shields.io/badge/License-MIT-lightgrey?style=flat-square)

---

## 🧠 What is PRISM?

PRISM is a fully local, autonomous data science agent designed for users who need powerful AI-driven analytics **without ever uploading sensitive data to the cloud**. Powered by **Llama 3.2 / Qwen2.5-Coder** running locally via Ollama, PRISM interprets natural language queries, autonomously writes and executes analytical code, retrieves insights via RAG, and delivers structured reports — all on your own machine.

---

## ✨ Key Features

- 🔒 **100% Local Execution** — No data leaves your device. No API calls to OpenAI, no cloud storage.
- 🤖 **Autonomous Agent** — Understands your query, plans, and executes without manual intervention.
- 📊 **Visualization Engine** — Generates charts and plots directly from natural language.
- 📝 **Statistical Summaries** — Produces structured statistical breakdowns on demand.
- 🔍 **RAG Pipeline** — Retrieves context from local datasets using vector search.
- 💻 **Code Execution** — Writes and runs Python code autonomously to answer analytical queries.
- 🌐 **Secure Remote Access** — Expose locally via Pinggy/Cloudflare tunnels without data leaving your environment.

---

## 🏗️ Architecture

```
User Query (Natural Language)
        │
        ▼
┌───────────────────┐
│  Query Classifier  │  ◄── LangGraph Router Node
└───────────────────┘
        │
   ┌────┴────┬──────────┬──────────┐
   ▼         ▼          ▼          ▼
[RAG]    [CodeGen]  [Visualize] [Summarize]
  │         │           │           │
  └────┬────┴───────────┴───────────┘
       ▼
  Structured Output
  (Report / Chart / Table)
       │
       ▼
  Streamlit UI
```

PRISM uses a **LangGraph multi-node conditional routing architecture** where each incoming query is classified and dispatched to one or more specialized agent nodes:

| Node | Responsibility |
|------|---------------|
| Query Classifier | Understands intent and routes to appropriate node(s) |
| RAG Retrieval | Vector search over local datasets via LangChain |
| Code Generator | Writes and executes Python analytics code |
| Chart Renderer | Produces matplotlib/plotly visualizations |
| Summarizer | Generates statistical summaries and insight reports |

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| LLM | Llama 3.2 / Qwen2.5-Coder (via Ollama) |
| Orchestration | LangChain + LangGraph |
| Vector Store | Local embeddings (ChromaDB / FAISS) |
| UI | Streamlit |
| Tunneling | Pinggy / Cloudflare |
| Runtime | Python 3.10+ |
| GPU | Kaggle T4 / Local CPU |

---

## 🚀 Getting Started

### Prerequisites

```bash
# Install Ollama
curl -fsSL https://ollama.com/install.sh | sh

# Pull the model
ollama pull llama3.2
# or for code-heavy tasks
ollama pull qwen2.5-coder:7b

# Clone the repo
git clone https://github.com/YOUR_USERNAME/PRISM.git
cd PRISM

# Install dependencies
pip install -r requirements.txt
```

### Run PRISM

```bash
streamlit run app.py
```

Open your browser at `http://localhost:8501` and start querying your data in plain English.

---

## 📁 Project Structure

```
PRISM/
├── prism_v1.ipynb      # V1: Cloud prototype — Groq API + LangGraph agentic pipeline
├── prism_v2.ipynb      # V2: Final local version — Ollama + LangGraph + Streamlit UI
├── requirements.txt
└── README.md
```

> Both notebooks are self-contained. All setup, routing logic, code execution, and UI are defined inline — no external modules needed.

---

## 📓 Development Journey

PRISM was built iteratively across multiple versions:

| Version | Stack | Description |
|---------|-------|-------------|
| **V1** `prism_v1.ipynb` | Groq API + LangGraph | Cloud-based prototype. Validated the agentic pipeline using Llama-3.3-70B via Groq. Fast iteration, external API dependency. |
| **V2** `prism_v2.ipynb` | Ollama + LangGraph + Streamlit | Final production version. Fully local, GPU-accelerated on Kaggle T4, zero cloud dependency. Complete Streamlit UI with chat interface. |

> The evolution from V1 → V2 reflects the core PRISM philosophy: **start fast in the cloud, then bring everything local for privacy.**

---

## 🔐 Why Local?

Most AI data tools send your data to remote servers for processing. PRISM is built on the principle that **your data never leaves your machine**:

- ✅ No OpenAI API keys needed
- ✅ Works fully offline after setup
- ✅ Safe for sensitive, proprietary, or personal datasets
- ✅ No usage costs or rate limits

---

## 📸 Demo

> *Screenshots / GIF coming soon*

---

## 🤝 Contributing

Pull requests are welcome! For major changes, please open an issue first to discuss what you'd like to change.

---

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

---

## 👥 Authors

- **Aditya** — M.Tech Data Science
- *Built as part of M.Tech project work*

---

> ⭐ If you find PRISM useful, consider giving it a star!
