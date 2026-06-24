# Social Media Analytics API

[![Live Demo](https://img.shields.io/badge/Live_Demo-View_API-blue)](https://social-media-api.onrender.com/docs)
[![GitHub](https://img.shields.io/badge/GitHub-Repo-black)](https://github.com/vinay-jawahrani/Social-Media-Analytics)

A secure RESTful backend API for a social media platform built with FastAPI, PostgreSQL, and JWT authentication.

## 🚀 Features

- **User Authentication** – Register and login with JWT tokens
- **Password Security** – Bcrypt hashing for secure password storage
- **Post Management** – Create, read, and manage posts
- **Protected Routes** – JWT-based authentication for sensitive endpoints
- **Database Integration** – PostgreSQL with SQLAlchemy ORM
- **Auto-generated Docs** – Swagger UI at `/docs`
- **Environment Configuration** – Secure environment variables with `.env`

## 🛠️ Tech Stack

- **Framework**: FastAPI
- **Database**: PostgreSQL
- **ORM**: SQLAlchemy
- **Authentication**: JWT + bcrypt
- **Deployment**: Render

## 📌 API Endpoints

| Method | Endpoint | Description | Auth Required |
|--------|----------|-------------|---------------|
| POST | `/api/users/register` | Register a new user | ❌ |
| POST | `/api/auth/login` | Login and get JWT token | ❌ |
| GET | `/api/users/me` | Get current user details | ✅ |
| GET | `/api/users/{user_id}` | Get user by ID | ❌ |
| POST | `/api/posts` | Create a new post | ✅ |
| GET | `/api/posts` | Get all posts (paginated) | ❌ |
| GET | `/api/posts/{post_id}` | Get a single post | ❌ |
| GET | `/api/posts/me` | Get user's own posts | ✅ |

## 📦 Installation & Setup

### Prerequisites
- Python 3.10+
- PostgreSQL
- Git

### Steps

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/Social-Media-Analytics.git
   cd Social-Media-Analytics
Create and activate virtual environment:

bash
python -m venv venv
# Windows:
venv\Scripts\activate
# Mac/Linux:
source venv/bin/activate
Install dependencies:

bash
pip install -r requirements.txt
Create .env file:

text
DATABASE_URL=postgresql://postgres:your_password@localhost:5432/social_media_db
SECRET_KEY=your-super-secret-key
Create the database:

sql
CREATE DATABASE social_media_db;
Run the server:

bash
uvicorn app.main:app --reload
Access the API:

API: http://127.0.0.1:8000

Swagger Docs: http://127.0.0.1:8000/docs

🧪 API Testing
Register a User
bash
curl -X POST http://127.0.0.1:8000/api/users/register \
  -H "Content-Type: application/json" \
  -d '{"username":"testuser","email":"test@example.com","password":"mypassword"}'
Login
bash
curl -X POST http://127.0.0.1:8000/api/auth/login \
  -H "Content-Type: application/x-www-form-urlencoded" \
  -d "username=testuser&password=mypassword"
Create a Post (Requires Token)
bash
curl -X POST http://127.0.0.1:8000/api/posts \
  -H "Authorization: Bearer YOUR_TOKEN_HERE" \
  -H "Content-Type: application/json" \
  -d '{"title":"My First Post","content":"This is my first post."}'
Get All Posts
bash
curl http://127.0.0.1:8000/api/posts
Get User's Own Posts (Requires Token)
bash
curl -X GET http://127.0.0.1:8000/api/posts/me \
  -H "Authorization: Bearer YOUR_TOKEN_HERE"
📁 Project Structure
text
Social-Media-Analytics/
├── app/
│   ├── __init__.py
│   ├── main.py          # FastAPI application
│   ├── database.py      # Database connection
│   ├── models.py        # SQLAlchemy models
│   ├── schemas.py       # Pydantic schemas
│   └── auth.py          # Authentication logic
├── venv/                # Virtual environment (ignored)
├── .env                 # Environment variables (ignored)
├── requirements.txt     # Dependencies
├── render.yaml          # Render deployment config
└── README.md            # Project documentation
🔐 Environment Variables
Variable	Description	Required
DATABASE_URL	PostgreSQL connection string	✅
SECRET_KEY	JWT secret key ✅

🐳 Deployment
This project is deployed on Render:

Connect your GitHub repository

Set Build Command: pip install -r requirements.txt

Set Start Command: uvicorn app.main:app --host 0.0.0.0 --port $PORT

Add environment variables in Render dashboard

Deploy and get a live URL

🎯 Live Demo
API URL: https://social-media-api.onrender.com

Swagger Docs: https://social-media-api.onrender.com/docs

📄 License
MIT

👤 Author
Vinay Jawahrani

GitHub: @vinay-jawahrani

🌟 Show Your Support
If you found this project useful, give it a ⭐ on GitHub!
