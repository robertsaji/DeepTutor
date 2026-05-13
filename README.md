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
2. Create your feature branch (`git checkout -b feat/amazing-feature`)
3. Commit your changes (`git commit -m 'feat: add amazing feature'`)
4. Push to the branch (`git push origin feat/amazing-feature`)
5. Open a Pull Request

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgements

- Original project: [HKUDS/DeepTutor](https://github.com/HKUDS/DeepTutor)
- Built with [LangChain](https://github.com/langchain-ai/langchain)
- UI powered by [Gradio](https://github.com/gradio-app/gradio)
