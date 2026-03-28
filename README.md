# 🚀 Multi-Agent GenAI Platform
**Autonomous Research • LLM Reasoning • Vector Search • Media Generation • Cloud-Native Architecture**

<p align="center">
  <a href="https://github.com/rathishbarath/multi-agent-genai-platform/actions/workflows/ci.yaml">
    <img src="https://github.com/rathishbarath/multi-agent-genai-platform/actions/workflows/ci.yaml/badge.svg" alt="CI" />
  </a>
  <a href="https://github.com/rathishbarath/multi-agent-genai-platform/actions/workflows/e2e-celery.yml">
    <img src="https://github.com/rathishbarath/multi-agent-genai-platform/actions/workflows/e2e-celery.yml/badge.svg" alt="E2E Celery" />
  </a>
  <a href="https://github.com/rathishbarath/multi-agent-genai-platform/actions/workflows/cd.yaml">
    <img src="https://github.com/rathishbarath/multi-agent-genai-platform/actions/workflows/cd.yaml/badge.svg" alt="CD" />
  </a>
  <img src="https://img.shields.io/badge/Python-3.10_|_3.11-blue" alt="Python" />
  <img src="https://img.shields.io/badge/FastAPI-Backend-teal" alt="FastAPI" />
  <img src="https://img.shields.io/badge/Next.js-Frontend-black" alt="Next.js" />
  <img src="https://img.shields.io/badge/Kubernetes-Ready-blue" alt="Kubernetes" />
  <img src="https://img.shields.io/badge/License-Apache_2.0-green" alt="License" />
</p>

---

## 📌 Overview

A **production-grade multi-agent GenAI orchestration platform** that autonomously handles end-to-end research workflows:

- Semantic retrieval from Semantic Scholar + arXiv  
- Structured LLM reasoning & summarization  
- Vector embedding & Pinecone indexing  
- Automated PPT slide + narrated video generation  
- Distributed execution via Celery workers  
- Modern Next.js frontend with real-time task tracking  
- Full observability (Prometheus, Grafana, OpenTelemetry)  
- Kubernetes-ready deployment via Helm + GitHub Actions CI/CD  

Built with enterprise architecture patterns used at scale.

---

## 🏗 Architecture

<img width="1536" height="1024" alt="System Architecture" src="https://github.com/user-attachments/assets/482aee61-232d-402c-8698-593d1ac7a8a2" />

---

## 🧱 End-to-End Layers

### **Frontend** (Next.js 14)
- Dashboard, task status, workflow triggers  
- Secure SSR + proxy to backend  

### **Backend** (FastAPI)
- JWT/OAuth2 auth, research orchestration, LLM calls, embeddings, media endpoints  

### **Worker Layer** (Celery)
- Long-running async jobs: research → summarization → vector ingestion → PPT/Video generation  

### **ML & Storage**
- Pinecone vector DB, Redis cache, PostgreSQL, S3/MinIO for media  

### **Observability & DevOps**
- Prometheus metrics, Grafana dashboards, OpenTelemetry tracing, Sentry  
- Kubernetes + Helm, GitHub Actions CI/CD  

---

## 🌟 Key Features

- **Multi-Agent Orchestration** — SearchAgent, SummarizerAgent, EmbeddingsAgent, MediaAgent  
- **Distributed Pipeline** — Async FastAPI + Celery + Redis/RabbitMQ  
- **Semantic Search & Retrieval** — SentenceTransformers + Pinecone (with SQLite fallback)  
- **Media Generation** — PPT (python-pptx) + narrated video (MoviePy + gTTS)  
- **Production Observability** — `/metrics`, OTEL traces, Grafana dashboards  
- **Enterprise Security** — JWT, rate limiting, PodSecurity, NetworkPolicies  

---

## ⚙️ Tech Stack

| Layer              | Technologies                              |
|--------------------|-------------------------------------------|
| Frontend           | Next.js 14, React, Tailwind              |
| Backend            | FastAPI, SQLModel, Celery, Redis         |
| Vector Search      | Pinecone, SentenceTransformers           |
| Workers            | Celery, MoviePy, python-pptx             |
| Database           | PostgreSQL                               |
| Infrastructure     | Docker, Kubernetes, Helm                 |
| Observability      | Prometheus, Grafana, OpenTelemetry, Sentry |
| CI/CD              | GitHub Actions, DockerHub                |

---

## 🧪 Quickstart

```bash
git clone https://github.com/rathishbarath/autoscilab
```

**Backend**
```bash
cd backend/api
pip install -r requirements.txt
uvicorn main:app --reload
```

**Celery Worker**
```bash
cd backend/workers
celery -A api.workers.celery_app.celery_app worker --loglevel=info
```

**Frontend**
```bash
cd frontend/nextjs-app
npm install
npm run dev
```

**Full Stack (Docker)**
```bash
cd infra
docker-compose up --build
```

Create `.env` in `backend/api/` with your keys (LLM, Pinecone, etc.).

---

## 📊 Observability

- **Metrics**: `GET /metrics` (Prometheus)
- **Dashboards**: `grafana/dashboard_full.json` & `grafana/dashboard_enterprise.json`
- **Traces**: OpenTelemetry on all FastAPI routes, Celery tasks, and LLM calls

---

## 📘 API Endpoints (Key)

- `POST /agents/start_research` → Full research → media pipeline  
- `GET /agents/task_status/{task_id}` → Summary, PPT URL, Video URL, status  
- `GET /research/search?q=...` → Semantic lookup  

---

## 🎥 Demo

[Demo GIF](https://github.com/rathishbarath/multi-agent-genai-platform/blob/main/demo.gif)  
*(Generate locally: `bash scripts/generate_demo_gif.sh`)*

---

## 🤝 Contributing

We follow Conventional Commits. PRs welcome!

## 📄 License

Apache 2.0

---

**Made by [Rathish Barath](https://github.com/rathishbarath)**
