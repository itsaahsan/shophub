# 🛒 Shop Hub — Full-Stack AI E-Commerce Platform

[![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)](https://fastapi.tiangolo.com/)
[![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://reactjs.org/)
[![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white)](https://www.mongodb.com/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

Shop Hub is a production-grade AI-powered e-commerce platform built with modern technologies. It features AI-driven product recommendations, seamless Stripe payments, and a high-performance Redis-cached catalog.

## ✨ Features

- **Auth**: JWT-based authentication with httpOnly cookies, Google OAuth, and secure password hashing.
- **AI Engine**: Personalized product recommendations using OpenAI GPT-3.5 and category-based similarity.
- **Payments**: Full Stripe integration with webhooks for secure order processing.
- **Admin**: Comprehensive dashboard with Recharts for sales analytics and full inventory management.
- **Performance**: Sub-200ms API response times with Upstash Redis caching.
- **Media**: Automated image uploads and transformations via Cloudinary.
- **Design**: Fully responsive UI built with Tailwind CSS.

## 🚀 Tech Stack

- **Frontend**: React 19, TypeScript, Vite, Tailwind CSS, Zustand, TanStack Query.
- **Backend**: FastAPI (Python), Motor (Async MongoDB), Redis (Upstash).
- **Services**: OpenAI API, Stripe, Cloudinary, Google OAuth.
- **Testing**: Pytest (Backend), Vitest & RTL (Frontend).

## 🛠️ Installation

### Prerequisites

- Node.js 18+
- Python 3.10+
- MongoDB (local or Atlas)
- Redis (Upstash recommended)

### Backend Setup

```powershell
cd backend
python -m venv venv
.\venv\Scripts\Activate.ps1
pip install -r requirements.txt
```

Copy `.env.example` to `.env` and configure the following required variables:

```env
# App
APP_NAME="Shop Hub API"
DEBUG=True
API_V1_PREFIX="/api/v1"
FRONTEND_URL="http://localhost:5173"

# MongoDB
MONGODB_URI="mongodb://localhost:27017"
MONGODB_DB_NAME="shophub"

# JWT (generate a secure random string for production)
JWT_SECRET="your-secret-key"
JWT_ALGORITHM="HS256"
ACCESS_TOKEN_EXPIRE_MINUTES=30
REFRESH_TOKEN_EXPIRE_DAYS=7

# Stripe (get from Stripe Dashboard)
STRIPE_SECRET_KEY="sk_test_..."
STRIPE_WEBHOOK_SECRET="whsec_..."
STRIPE_PUBLISHABLE_KEY="pk_test_..."

# OpenAI (get from OpenAI Platform)
OPENAI_API_KEY="sk-..."

# Cloudinary (get from Cloudinary Dashboard)
CLOUDINARY_CLOUD_NAME="..."
CLOUDINARY_API_KEY="..."
CLOUDINARY_API_SECRET="..."

# Redis (create at Upstash)
REDIS_URL="rediss://default:...@...upstash.io:6379"

# Google OAuth (create at Google Cloud Console)
GOOGLE_CLIENT_ID="..."
GOOGLE_CLIENT_SECRET="..."

# Email (SMTP)
SMTP_HOST="smtp.gmail.com"
SMTP_PORT=587
SMTP_USER="your-email@gmail.com"
SMTP_PASSWORD="your-app-password"
```

Start the backend server:

```powershell
uvicorn app.main:app --reload
```

The API will be available at `http://127.0.0.1:8000`

### Frontend Setup

```powershell
cd frontend
npm install
```

Copy `.env.example` to `.env` and configure:

```env
VITE_API_URL="http://localhost:8000/api/v1"
VITE_GOOGLE_CLIENT_ID="your-google-client-id"
```

Start the development server:

```powershell
npm run dev
```

The UI will be available at `http://localhost:5173`

## 📄 API Documentation

- Interactive Docs: `http://localhost:8000/docs`
- Redoc: `http://localhost:8000/redoc`

## 🧪 Testing

### Backend Tests

```powershell
cd backend
pytest
```

### Health Check

```powershell
python health_check.py
```

## 🌍 Deployment Guide

### MongoDB Atlas

1. Create a free cluster on [MongoDB Atlas](https://www.mongodb.com/cloud/atlas).
2. Get your connection string and add it to `MONGODB_URI` in `.env`.

### Upstash Redis

1. Create a Redis database on [Upstash](https://upstash.com/).
2. Copy the Redis URL to `REDIS_URL`.

### Render (Backend)

1. Connect your GitHub repo to [Render](https://render.com/).
2. Select "Web Service" and use `uvicorn app.main:app --host 0.0.0.0 --port $PORT`.
3. Add all environment variables from `backend/.env`.

### Vercel (Frontend)

1. Connect your GitHub repo to [Vercel](https://vercel.com/).
2. Set the build command to `npm run build` and output directory to `dist`.
3. Add `VITE_API_URL` (your Render URL) and other frontend env vars.

## 📁 Project Structure

```
shop-hub/
├── backend/
│   ├── app/
│   │   ├── api/          # API routes
│   │   ├── core/         # Config, security
│   │   ├── models/       # Database models
│   │   ├── schemas/      # Pydantic schemas
│   │   ├── services/     # Business logic
│   │   └── main.py       # FastAPI app
│   ├── tests/            # Backend tests
│   └── requirements.txt
├── frontend/
│   ├── src/
│   │   ├── components/   # React components
│   │   ├── pages/       # Page components
│   │   ├── hooks/       # Custom hooks
│   │   ├── services/    # API calls
│   │   ├── stores/     # Zustand stores
│   │   └── utils/       # Utilities
│   └── package.json
└── README.md
```

## 📝 License

MIT

---

Built with ❤️ for a showstopper portfolio.
"# shophub"  
