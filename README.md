# MERN + Docker Setup 🚀

This project demonstrates how to containerize a **MERN stack** (MongoDB, Express/Node backend, React frontend) using **Docker** and **Docker Compose**.  
It provides a reproducible development environment where the frontend, backend, and database each run in their own containers.

---

## 📦 Project Structure

mern-docker/
│
├── frontend/ # React app (Vite-based or CRA)
│ └── Dockerfile # Dockerfile for frontend service
│
├── backend/ # Node.js + Express API
│ └── Dockerfile # Dockerfile for backend service
│
├── docker-compose.yml
├── .env.example # Example environment variables
└── README.md


---

## ⚙️ Services

### **Frontend (web)**
- Runs on port `5555` (mapped to container’s port 5555).
- Uses `VITE_API_URL` to communicate with the backend API.
- Hot-reload enabled in Docker for local development.

### **Backend (api)**
- Runs on port `7777`.
- Connects to MongoDB using `DB_URL` (default: `mongodb://db/anime`).
- Express API for handling requests from the frontend.

### **Database (db)**
- MongoDB container (`mongo:latest`).
- Persists data in a Docker volume called `anime`.
- Exposes port `27017`.

---

## 🔑 Environment Variables

Copy `.env.example` → `.env` and set your own values:

```bash
cp .env.example .env
