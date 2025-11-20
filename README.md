
# WhatsApp Product Review Collector

This project is a full-stack application that collects product reviews from users via WhatsApp and displays them on a frontend interface. The system integrates WhatsApp messaging using Twilio, processes input using a Python backend (FastAPI/Flask/Django), stores data in PostgreSQL, and exposes REST APIs consumed by a React frontend.

## 🚀 Features

- Users submit reviews directly from WhatsApp  
- Conversation-based data collection:
  - Product Name  
  - User Name  
  - Review Text  
- Data stored in **Postgres**  
- Public API endpoint to fetch stored reviews  
- React UI that displays all reviews

## 🛠 Tech Stack

| Component | Technology |
|----------|------------|
| Backend | FastAPI / Flask / Django (Python) |
| Database | PostgreSQL |
| Messaging | Twilio WhatsApp Sandbox |
| Frontend | React.js |
| ORM (optional) | SQLAlchemy / Django ORM |

## 📂 Database Schema

| Column | Type | Description |
|--------|------|------------|
| `id` | unique id | Primary Key |
| `contact_number` | text | WhatsApp number |
| `user_name` | text | Name of reviewer |
| `product_name` | text | Product being reviewed |
| `product_review` | text | Review message |
| `created_at` | timestamp | Created timestamp |

## 🔗 API Endpoints

### GET /api/reviews
Returns all stored reviews in JSON format.

### Sample Response
```json
[
  {
    "id": 1,
    "contact_number": "+1415XXXXXXX",
    "user_name": "Aditi",
    "product_name": "iPhone 15",
    "product_review": "Amazing battery life",
    "created_at": "2025-11-17T12:34:56Z"
  }
]
```

## 📞 WhatsApp Flow

Example conversation:

```
User: Hi
Bot: Which product is this review for?

User: iPhone 15
Bot: What's your name?

User: Aditi
Bot: Please send your review for iPhone 15.

User: Amazing battery life, very satisfied.
Bot: Thanks Aditi -- your review for iPhone 15 has been recorded.
```

## ▶️ How to Run the Project

### 1️⃣ Clone Repository
```sh
git clone <repo-url>
cd project
```

### 2️⃣ Create Virtual Environment
```sh
python -m venv venv
source venv/bin/activate    # Windows: venv\Scripts\activate
```

### 3️⃣ Install Dependencies
```sh
pip install -r requirements.txt
```

### 4️⃣ Setup PostgreSQL

Create database and configure `.env`:

```
DB_HOST=localhost
DB_NAME=reviews
DB_USER=postgres
DB_PASS=password
```

### 5️⃣ Start Backend
```sh
uvicorn main:app --reload
```

### 6️⃣ Configure Twilio WhatsApp Sandbox

Connect webhook to:
```
https://<your-server>/webhook
```

### 7️⃣ Start Frontend
```sh
npm install
npm run dev
```

## 📦 Deliverables

- GitHub Repository (Backend + Frontend)
- Screencast Demo
- Proper README.md

