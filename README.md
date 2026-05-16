# ☕ Raft Coffee

> **Mood-based specialty coffee, powered by AI** — a full-stack web application for Raft Coffee, Lahore, Pakistan.

[![React](https://img.shields.io/badge/React-18-61DAFB?logo=react&logoColor=white)](https://reactjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
[![FastAPI](https://img.shields.io/badge/FastAPI-0.100+-009688?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-3-06B6D4?logo=tailwindcss&logoColor=white)](https://tailwindcss.com/)
[![Supabase](https://img.shields.io/badge/Supabase-Auth-3ECF8E?logo=supabase&logoColor=white)](https://supabase.com/)

---

## What is this?

Raft Coffee is a full-stack specialty coffee shop web application that goes beyond a standard menu. Tell the AI chatbot how you feel, and it recommends the perfect coffee for that moment. Built with a React frontend, a FastAPI + LangChain backend, and a RAG pipeline powered by Groq's Llama models.

---

## Features

- 🤖 **AI Chatbot** — Mood-based coffee recommendations using Retrieval-Augmented Generation (RAG)
- 🛒 **Shopping Cart** — Add, remove, update items with quantity and customization (size, flavor)
- 📋 **Menu Browsing** — Signature, classic, and seasonal categories
- 🔐 **Admin Dashboard** — Secure login and session management via Supabase Auth
- 📱 **Fully Responsive** — Mobile-first design with Tailwind CSS and Radix UI

---

## Architecture

```
Frontend (React + TypeScript + Vite + Tailwind)
        │
        ▼
Backend (FastAPI + LangChain + Groq API)
        │
        ▼
FAISS Vector Store (Embeddings + Retrieval)
        │
        ▼
Supabase (Authentication)
```

### AI Chatbot Flow

```
User Message
     ↓
FastAPI /api/chat endpoint
     ↓
FAISS Retrieval — semantic search over coffee knowledge base
     ↓
Prompt + Context + Query → Groq LLM (Llama)
     ↓
Response streamed to frontend
```

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend | React 18, TypeScript, Vite, Tailwind CSS, Radix UI, React Router |
| Backend | FastAPI, Uvicorn, LangChain, Pydantic |
| AI / ML | Groq API (Llama), FAISS, Sentence Transformers (`all-MiniLM-L6-v2`) |
| Auth | Supabase Authentication |
| Icons | Lucide React |

---

## Project Structure

```
raft-coffee/
├── frontend/
│   └── src/
│       ├── components/
│       ├── contexts/
│       ├── pages/
│       ├── data/
│       └── App.tsx
├── backend/
│   ├── app/
│   │   ├── core/
│   │   ├── routes/
│   │   ├── services/
│   │   └── main.py
│   ├── scripts/
│   │   └── ingest.py
│   └── requirements.txt
└── data/
```

---

## Getting Started

### Prerequisites

- Node.js 18+
- Python 3.10+
- A [Groq API key](https://console.groq.com/)
- A [Supabase](https://supabase.com/) project

---

### Frontend

```bash
cd frontend
npm install
npm run dev
```

Runs at `http://localhost:8080`

---

### Backend

```bash
cd backend

# Create and activate virtual environment
python -m venv venv
venv\Scripts\activate        # Windows
source venv/bin/activate     # macOS / Linux

# Install dependencies
pip install -r requirements.txt

# Build the FAISS vector store
python scripts/ingest.py

# Start the API server
python -m app.main
```

Runs at `http://localhost:5000`

---

### Environment Variables

Create a `.env` file inside `/backend`:

```env
PORT=5000
GROQ_API_KEY=your_groq_api_key_here
```

---

## API Reference

| Method | Endpoint | Description |
|---|---|---|
| GET | `/` | Health check |
| POST | `/api/chat` | Send a message, receive a coffee recommendation |

---

## Performance

| Metric | Value |
|---|---|
| Cold start (AI model load) | 30–60 seconds |
| Chat response time (warm) | ~1–2 seconds |
| FAISS vector retrieval | < 10ms |

---

## 🎥 Project Demo

Watch the full project demonstration video here:  
➡️ [Raft Coffee Website Demo](https://github.com/meerabijaz/Raft-Coffee-Website-Demo/blob/main/raft-demo_YQrctfgs.mp4)


## Deployment

| Layer | Recommended Platforms |
|---|---|
| Frontend | Vercel, Netlify |
| Backend | Render, Railway, AWS |
| Auth | Supabase (managed) |

---

## Security

- Admin routes protected via Supabase session authentication
- API keys stored in environment variables — never committed to source control
- CORS configured to allow only the frontend origin

---
## Contributers 
- Meerab Ijaz
- Tooba Kaleem 
- Zarabee Maryam
- Atif Amir

