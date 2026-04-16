# Async Document Processing Workflow

This project is a full-stack system designed to process documents asynchronously while providing real-time progress updates to users. It demonstrates how background job processing can be combined with a modern web interface for a smooth user experience.

---

## 🚀 Overview

The application allows users to upload documents, process them in the background, track their progress live, and export structured results.
It focuses on building a scalable pipeline using asynchronous workers and event-driven updates.

---

## 🛠️ Tech Stack

* **Frontend:** Next.js (TypeScript)
* **Backend:** FastAPI
* **Database:** PostgreSQL
* **Queue System:** Celery
* **Messaging:** Redis (Pub/Sub)
* **Containerization:** Docker & Docker Compose

---

## ⚙️ How It Works

1. Users upload documents through the frontend.
2. The backend stores metadata and queues a background task.
3. Celery workers process documents step-by-step.
4. Progress updates are pushed via Redis.
5. The frontend receives live updates using Server-Sent Events (SSE).
6. Users can review, edit, and export processed data.

---

## 🔄 Processing Flow

Each document goes through multiple stages:

* Job started
* Parsing document
* Extracting fields
* Storing results
* Completion / failure handling

---

## 📁 Project Structure

* `backend/` → FastAPI APIs, Celery workers, business logic
* `frontend/` → User interface built with Next.js
* `sample_files/` → Test input documents
* `sample_exports/` → Example outputs

---

## 🌐 API Highlights

* Upload documents
* Track processing status
* Stream live progress updates
* Retry failed tasks
* Export results (JSON / CSV)

---

## 🧪 Running Locally (Docker)

```bash
docker compose up --build
```

* Frontend → http://localhost:3000
* Backend Docs → http://localhost:8000/docs

---

## 🧪 Running Without Docker

### Backend

```bash
cd backend
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
uvicorn app.main:app --reload
```

### Worker

```bash
celery -A app.workers.celery_app.celery_app worker -l info
```

### Frontend

```bash
cd frontend
npm install
npm run dev
```

---

## 📌 Key Features

* Asynchronous background processing
* Real-time progress tracking (SSE)
* Retry mechanism for failed jobs
* Export functionality (JSON / CSV)
* Multi-service architecture using Docker

---

## 🎯 What This Project Demonstrates

* Designing async systems using queues
* Handling long-running tasks efficiently
* Real-time communication between backend and frontend
* Full-stack integration with modern tools

---

## 📎 Note

This project is built for learning and demonstrating backend architecture concepts such as task queues, event streaming, and scalable system design.



## AI Usage Note
This project was developed with AI-assisted support.
