# 🌍 Probas-Sathi (প্রবাস-সাথী)

**A Full-Stack Smart AI Web Application for Bangladeshi Expatriates**

> Final Project for the *AI Engineering* course at **ICT Bangladesh**.

## 📖 About the Project

**Probas-Sathi** is designed to be a "Smart Digital Companion" for our remittance fighters—Bangladeshi expatriates living abroad. Every day, they face numerous challenges, including language barriers, lack of legal knowledge, fraudulent visa/job scams, and a lack of immediate support during emergencies.

I built this platform to provide a unified, secure, and highly intelligent solution. It acts as an all-in-one hub that provides safety alerts, career tools, medical consultation booking, and a highly advanced AI Agent that can communicate in native languages and execute real-world tasks on behalf of the user.

## ✨ Key Features & Use Cases

Out of over 30+ integrated features, here are the core functionalities:

* 🤖 **Wejard AI Agent (Local Llama 3.2):** Powered by a local LLM and RAG architecture, this AI not only answers legal and general queries in any language (text & voice) but can also execute tasks like booking transport, finding halal food nearby, and assisting with insurance claims.

* 🚨 **Automated Embassy SOS:** In an emergency, a single click (or voice command to the AI) triggers an automated SOS message with the user's live GPS location to the nearest Bangladesh Embassy.

* 🛡️ **AI Scam Detector:** Users can upload job offers or visa documents, and the AI will scan and verify their authenticity to prevent fraud.

* 💼 **Pro CV Builder:** A 1-click professional PDF resume generator tailored for overseas jobs (includes auto-download functionality using `html2pdf.js`).

* 💸 **Finance & Career Hub:** Live remittance rate tracker, salary & overtime calculator, and an integrated job portal.

* 🩺 **Health & Wellness:** Includes Telemedicine booking, Mental Health counseling chats, and Emergency contact directories (all assisted by specialized AI roles).

## 🛠️ Technology Stack

This is a modern Full-Stack application built with performance, security, and AI at its core:

* **Frontend:** Next.js, React, Tailwind CSS (featuring a premium *Glassmorphism* UI).
* **Backend:** FastAPI (Python) - ensuring high speed and robust RESTful APIs.
* **Database:** PostgreSQL with SQLAlchemy ORM (auto-generating 30+ relational tables).
* **AI Integration:** Ollama running **Llama 3.2** locally (ensuring 100% data privacy) and Web Speech API for voice interactions.
* **Security:** OAuth2 and JWT (JSON Web Tokens) for secure authentication.

## 📂 Detailed Project Structure

The project is divided into a robust Next.js frontend and a modular FastAPI backend, supporting over 30 distinct features.

```text
probas-sathi/
├── frontend/                      # Next.js Application (User Interface)
│   ├── src/
│   │   ├── app/                   # App Router (Pages & Layouts)
│   │   │   ├── (auth)/            # Login & Registration pages
│   │   │   ├── dashboard/         # Dashboard Layout & Feature Routes
│   │   │   │   ├── ai-assistant/  # Main AI Chatbot page
│   │   │   │   ├── cv-builder/    # Resume Generator (PDF Export)
│   │   │   │   ├── labor-laws/    # AI-powered Legal Advisor
│   │   │   │   ├── telemedicine/  # Doctor Booking & AI Medical Assistant
│   │   │   │   ├── mental-health/ # Mental Health Counseling Interface
│   │   │   │   ├── local-guide/   # AI Local Area & Halal Food Guide
│   │   │   │   ├── transport/     # AI Transport & Vehicle Booking
│   │   │   │   ├── document-expiry/# Document Tracking & Alerts
│   │   │   │   ├── sos/           # Emergency SOS & Alert Dashboard
│   │   │   │   └── ...            # (Remaining 20+ Feature Routes)
│   │   │   ├── globals.css        # Tailwind CSS & Custom Glassmorphism styles
│   │   │   └── layout.jsx         # Root Layout
│   │   └── components/            # Reusable UI Components
│   │       ├── layout/            # Navbar (with Notifications), Sidebar, Modals
│   │       ├── ui/                # Buttons, Cards, Input Fields
│   │       └── ReusableAIChat.jsx # Core AI Agent Component (Voice & Multi-lang support)
│   ├── public/                    # Images, Icons, Static assets
│   ├── tailwind.config.js         # Tailwind configuration
│   └── package.json               # Frontend dependencies
│
├── backend/                       # FastAPI Application (API & Logic)
│   ├── routers/                   # Modular API Route Handlers
│   │   ├── users.py               # Authentication & User Profile Management
│   │   ├── ai_chat.py             # Ollama (Llama 3.2) Integration endpoints
│   │   ├── sos.py                 # Emergency Alert System Logic
│   │   ├── telemedicine.py        # Medical Booking & Doctor APIs
│   │   ├── jobs.py                # Job Portal API
│   │   ├── finance.py             # Salary & Remittance Tracking API
│   │   └── ...                    # (API routers for all 30 features)
│   ├── core/
│   │   ├── security.py            # JWT Token generation, hashing, & validation
│   │   └── config.py              # Environment variables & App Settings
│   ├── main.py                    # Application Entry Point & CORS Setup
│   ├── models.py                  # SQLAlchemy Database Models (30+ Relational Tables)
│   ├── schemas.py                 # Pydantic Models for Request/Response Validation
│   ├── database.py                # PostgreSQL Connection & Engine Setup
│   └── requirements.txt           # Python dependencies (FastAPI, SQLAlchemy, etc.)
│
└── README.md                      # Project Documentation
```

## 🚀 Getting Started

### Prerequisites

* Node.js & npm (for frontend)
* Python 3.9+ (for backend)
* PostgreSQL installed and running
* [Ollama](https://ollama.com/) installed on your machine.

### 1. Run the AI Model (Local)

Open a terminal and run the Llama 3.2 model in the background. This will start the local inference server required for the AI Assistant.

```bash
ollama run llama3.2
```

### 2. Setup the Backend

Navigate to the backend directory, install requirements, and start the FastAPI server:

```bash
cd backend
pip install -r requirements.txt
uvicorn main:app --reload
```

*(The database tables will auto-generate upon starting the server via `models.Base.metadata.create_all`).*

### 3. Setup the Frontend

Navigate to the frontend directory, install packages, and run the Next.js app:

```bash
cd frontend
npm install
npm run dev
```

Open `http://localhost:3000` in your browser to view the application. The interactive Swagger UI for the backend API can be accessed at `http://127.0.0.1:8000/docs`.

## 🙏 Acknowledgements

A heartfelt thank you to the mentors and authorities at **ICT Bangladesh** for their incredible guidance throughout the *AI Engineering* course. Building a project of this scale from scratch taught me invaluable lessons in full-stack web development, backend architecture, and advanced Agentic AI integration. This project would not have been possible without their continuous support and world-class curriculum.