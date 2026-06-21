# Social Media Analytics API

A secure RESTful backend API for a social media platform built with FastAPI, PostgreSQL, and JWT authentication.

## 🚀 Features

- User registration and login with JWT authentication
- Password hashing using bcrypt
- CRUD operations for posts (create, read all, read single, read user's own posts)
- PostgreSQL database with SQLAlchemy ORM
- Auto-generated Swagger UI documentation (`/docs`)
- Environment-based configuration using `.env`
- Docker containerization for easy deployment

## 🛠️ Tech Stack

- **Framework**: FastAPI
- **Database**: PostgreSQL
- **ORM**: SQLAlchemy
- **Authentication**: JWT + bcrypt
- **Deployment**: Docker (optional)
- **Documentation**: OpenAPI / Swagger UI

## 📦 Installation & Setup

### Prerequisites

- Python 3.10 or higher
- PostgreSQL
- Git

### Steps

1. **Clone the repository:**
   ```bash
   git clone https://github.com/your-username/social-media-analytics.git
   cd social-media-analytics
