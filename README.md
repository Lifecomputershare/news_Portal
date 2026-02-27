# 📰 News Portal API

A RESTful News Portal system built with role-based authentication and full CRUD functionality for managing news, categories, comments, and users.

---

## 🚀 Features

- User Signup & Login
- Role-Based Access Control (`admin`, `editor`, `user`)
- Create, Update, Delete News
- Draft & Published Status
- View Counter System
- Comments System
- Category Management
- Feature Image Upload
- Slug-Based News Detail API

---

## 🏗 Project Overview

This project provides:

- 🔐 Authentication APIs
- 📰 News Management APIs
- 📂 Category APIs
- 👤 Role-Based Dashboard Logic

---

# 🗄 Database Models

## 1️⃣ RegisterUser

| Field | Type | Description |
|-------|------|------------|
| id | Integer | Primary Key |
| username | String | Unique username |
| email | String | User email |
| password | Hashed String | Secure password |
| roles | Enum | admin, editor, user |
| created_at | DateTime | Account created time |
| updated_at | DateTime | Last updated time |

---

## 2️⃣ News

| Field | Type | Description |
|-------|------|------------|
| id | Integer | Primary Key |
| title | String | News title |
| description | Text | News content |
| views | Integer | View counter |
| public | Enum | published, draft |
| author | ForeignKey | Reference to RegisterUser |
| created_at | DateTime | Created date |
| updated_at | DateTime | Updated date |
| feature_image | Image | Featured image |
| comments | Text / Related Model | News comments |

---

## 3️⃣ Category

| Field | Type | Description |
|-------|------|------------|
| id | Integer | Primary Key |
| category_name | String | Category name |
| news | ForeignKey | Related news |

---

# 🔗 API Endpoints

## 🔐 Authentication

POST   /api/v1/auth/signup/  
POST   /api/v1/auth/login/

---

## 📰 News APIs

POST    /api/v1/news/create/  
PUT     /api/v1/news/update/<int:id>/  
DELETE  /api/v1/news/delete/<int:id>/  
GET     /api/v1/news/all_news/  
GET     /api/v1/news/new_details/<slug:title>/  
POST    /api/v1/news/comment/

---

## 📂 Category APIs

GET     /api/v1/category/  
POST    /api/v1/category/

---

# 🔐 Role Permissions

| Role   | Permissions |
|--------|------------|
| Admin  | Full CRUD access |
| Editor | Manage own news |
| User   | Read news & comment |

---

# ⚙️ Installation Guide

## 1️⃣ Clone Repository

git clone https://github.com/lifecomputershare/news-portal.git  
cd news-portal  

## 2️⃣ Create Virtual Environment

python -m venv env  

Activate environment:

Windows:
env\Scripts\activate  

Linux/Mac:
source env/bin/activate  

## 3️⃣ Install Dependencies

pip install -r requirements.txt  

## 4️⃣ Run Migrations

python manage.py makemigrations  
python manage.py migrate  

## 5️⃣ Run Server

python manage.py runserver  

---

# 📌 Business Logic

- Views automatically increment when a news detail endpoint is accessed.
- Slug-based routing improves SEO.
- Passwords are securely hashed.
- Role-based authorization protects restricted endpoints.

---

# 🛠 Tech Stack

- Backend: Django 
- Database: MySQL 
- Authentication:  Session Authentication
- Media Handling: Local Storage 

---

# 📈 Future Improvements

- Pagination
- Search & Filtering
- Like/Dislike System
- Email Verification
- Social Login
- Admin Analytics Dashboard

