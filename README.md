# EvalVision AI

## Project Description

EvalVision AI is an intelligent platform designed for teachers to automate the evaluation of student exams and assignments. Driven by AI technologies, it drastically cuts down grading time whilst maintaining high accuracy, consistency, and providing constructive feedback directly derived from uploaded rubrics.

## Features

- **Automated AI Grading:** Utilizes LLMs to score answers according to a custom teacher-uploaded rubric document.
- **OCR Text Extraction:** Seamlessly extracts text from images and PDF uploads of student exams.
- **Plagiarism Checker:** Uses a robust semantic string-matching methodology strictly geared toward evaluating structural similarities among assignments in a batch.
- **Exam Management Dashboard:** Create and structure Exams (Long Qs, Short Qs, MCQs, Max marks) coupled with analytics.
- **Manual Overrides:** Teachers can intuitively override generated scores, view the breakdown of total evaluation points, and update criteria feedbacks through a seamless React dashboard.

## Tech Stack

### Frontend (Client)
- **Framework:** React.js + Vite
- **Styling:** Tailwind CSS
- **Routing:** React Router DOM
- **Charts:** Recharts

### Backend (Server)
- **Framework:** Node.js + Express.js
- **Database:** MongoDB (Mongoose ORM)
- **Authentication:** JWT (JSON Web Tokens)
- **Architecture:** Hexagonal Architecture

### AI Evaluation Service
- **Language / Framework:** Python + FastAPI
- **LLM Integration:** Google Gemini Models API

## Setup Instructions

### Prerequisites

- Node.js (v18+)
- Python (3.10+)
- MongoDB (Running locally or MongoDB Atlas)

### Environment Variables

Before running the services, you will need to create the following `.env` files in their respective directories.

**1. `server/.env`**
```env
# Required
MONGODB_URI=mongodb+srv://<username>:<password>@cluster0.example.mongodb.net/evalvision
JWT_SECRET=your_super_secret_jwt_key

# Optional (Defaults shown)
PORT=5000
NODE_ENV=development
JWT_EXPIRES_IN=1d
CLIENT_ORIGIN=http://localhost:5173
AI_SERVICE_URL=http://localhost:8001
```

**2. `client/.env`**
```env
# Optional. Backend API URL mapping (Defaults to http://localhost:5000/api if not set)
VITE_API_BASE_URL=http://localhost:5000/api
```

**3. `ai-service/.env`**
```env
# Required. Your Google Gemini API key
GEMINI_API_KEY=your_gemini_api_key_here

# Optional (Defaults shown)
GEMINI_MODEL=gemini-flash-lite-latest
```

### Installation

1. **Clone the repository:**
   ```bash
   git clone <YOUR_REPO_URL>
   cd EvalVision
   ```

2. **Backend Setup:**
   ```bash
   cd server
   npm install
   npm run dev
   ```

3. **Frontend Setup:**
   ```bash
   cd client
   npm install
   npm run dev
   ```

4. **AI Python Service Setup:**
   ```bash
   cd ai-service
   python -m venv .venv
   source .venv/Scripts/activate # On Windows PowerShell: .venv\Scripts\activate
   pip install -r requirements.txt
   uvicorn app.main:app --reload --port 8000
   ```
