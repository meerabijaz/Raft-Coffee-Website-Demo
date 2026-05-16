# Raft Coffee — Brew Bloom Design

Mood-based specialty coffee shop web app for **Raft Coffee**, Lahore.

## Project Structure

```
brew-bloom-design/
├── frontend/      ← React + TypeScript + Vite + TailwindCSS
└── backend/       ← FastAPI Backend (Python)
```

## Getting Started (Windows)

### 1. Frontend Setup
```powershell
cd frontend
npm install
npm run dev
```
The frontend will be available at `http://localhost:8080`.

### 2. Backend Setup
```powershell
cd backend

# Create virtual environment (first time)
python -m venv venv

# Activate virtual environment
.\venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Ingest data (one-time setup)
python scripts/ingest.py

# Run the server
python -m app.main
```
The backend API will be available at `http://localhost:5000`.

> [!NOTE]
> The first time you start the backend, it may take 30-60 seconds to load the AI search engine. Once loaded, all chat responses will be processed in milliseconds.

## Environment Variables
The backend requires a `.env` file in the `backend/` directory with the following:
```env
PORT=5000
GROQ_API_KEY=your_groq_api_key_here
```

