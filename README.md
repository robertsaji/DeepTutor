# DeepTutor 🎓

An intelligent tutoring system powered by large language models, designed to provide personalized learning experiences through interactive document-based Q&A.

> Fork of [HKUDS/DeepTutor](https://github.com/HKUDS/DeepTutor)

## ✨ Features

- 📄 **Document Understanding** — Upload PDFs and interact with their content
- 🤖 **Multi-LLM Support** — Compatible with OpenAI, Anthropic, DeepSeek, and local models
- 🧠 **RAG Pipeline** — Retrieval-Augmented Generation for accurate, grounded answers
- 💬 **Conversational Interface** — Maintain context across multi-turn dialogues
- 🌐 **Multilingual** — Supports both English and Chinese interfaces
- 🐳 **Docker Ready** — Easy deployment with Docker and Docker Compose

## 🚀 Quick Start

### Prerequisites

- Python 3.10+
- Node.js 18+ (for frontend)
- Docker & Docker Compose (optional)

### Installation

1. **Clone the repository**

```bash
git clone https://github.com/your-org/DeepTutor.git
cd DeepTutor
```

2. **Set up environment variables**

```bash
cp .env.example .env
# Edit .env with your API keys and configuration
```

3. **Install dependencies**

```bash
pip install -r requirements.txt
```

4. **Run the application**

```bash
python app.py
```

### Docker Deployment

```bash
docker compose up -d
```

## ⚙️ Configuration

Copy `.env.example` to `.env` and configure the following:

| Variable | Description | Required |
|---|---|---|
| `OPENAI_API_KEY` | OpenAI API key | Optional |
| `ANTHROPIC_API_KEY` | Anthropic API key | Optional |
| `DEEPSEEK_API_KEY` | DeepSeek API key | Optional |
| `LLM_PROVIDER` | Active LLM provider | Yes |
| `EMBEDDING_MODEL` | Embedding model name | Yes |
| `VECTOR_DB_PATH` | Path to vector database | Yes |

For Chinese users, refer to `.env.example_CN` for region-specific configurations.

> **Personal note:** I'm running this locally with `LLM_PROVIDER=deepseek` and `EMBEDDING_MODEL=text-embedding-3-small` — works well for my use case and keeps costs low. I also set `VECTOR_DB_PATH=./data/vectordb` so everything stays self-contained in the project directory.
>
> **Tip:** If DeepSeek's API is rate-limiting you during peak hours, switching `LLM_PROVIDER=openai` with `gpt-4o-mini` is a good fallback — still cheap and noticeably more reliable.
>
> **Note:** I've also found it helpful to set `MAX_UPLOAD_SIZE_MB=50` in `.env` if you're working with larger academic PDFs — the default felt a bit restrictive.
>
> **Note:** If you're on macOS and hit a `sqlite3` version error on startup, run `pip install pysqlite3-binary` and add the following to the top of `app.py` before any other imports:
> ```python
> __import__('pysqlite3')
> import sys
> sys.modules['sqlite3'] = sys.modules.pop('pysqlite3')
> ```
> This patches the system sqlite3 with a newer version that ChromaDB requires.

## 🏗️ Architecture

```
DeepTutor/
├── app.py              # Main application entry point
├── backend/
│   ├── api/            # REST API routes
│   ├── core/           # Core RAG and LLM logic
│   ├── models/         # Data models
│   └── utils/          # Utility functions
├── frontend/           # Web UI
├── data/               # Document storage
└── docker-compose.yml  # Docker configuration
```

## 🤝 Contributing

Contributions are welcome! Please open an issue or submit a pull request.

1. Fork the repository
2. Create your feature branch (`git checkout -b feat/
