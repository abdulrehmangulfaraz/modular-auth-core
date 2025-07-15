# 🔐 modular-auth-core

A Simple, Pluggable Authentication System for FastAPI Projects

A lightweight FastAPI-based module featuring multi-role login, email OTP verification, and basic HTML templates. Designed for quick integration into small to medium-sized web apps — currently includes basic placeholder dashboards.

---

## 📑 Table of Contents

* [✅ Features](#-features)
* [🛠️ Technologies Used](#-technologies-used)
* [📁 Project Structure](#-project-structure)
* [🔧 Installation Guide](#-installation-guide)
* [⚙️ Configuration](#-configuration)
* [🗃️ Database Initialization](#-database-initialization)
* [▶️ Running the App](#-running-the-app)
* [📄 Notes](#-notes)
* [📬 Contact](#-contact)
* [📜 License](#-license)

---

## ✅ Features

* 🔐 Email + Password Authentication
* ✉️ OTP Verification (via email, with expiry)
* 🧑‍🤝‍🧑 Basic Role Support: `student`, `tutor`, `admin`
* 📁 File Upload Support (e.g. CNIC, CVs – validation included)
* 🌐 Basic HTML templates using Jinja2 (with placeholder content)
* 🔄 SQLite & PostgreSQL support (via SQLAlchemy)

---

## 🛠️ Technologies Used

| Component  | Tech                |
| ---------- | ------------------- |
| Backend    | FastAPI             |
| ORM        | SQLAlchemy          |
| Templates  | Jinja2              |
| Email      | aiosmtplib          |
| Passwords  | bcrypt              |
| Config     | python-dotenv       |
| DB Engines | SQLite / PostgreSQL |

---

## 📁 Project Structure

```
modular-auth-core/
├── backend/
│   ├── __init__.py
│   ├── database.py
│   ├── init_db.py
│   ├── main.py
│   └── models.py
│
├── frontend/
│   └── templates/
│       ├── admin.html              # "Welcome, Admin"
│       ├── base.html               # Basic layout
│       ├── login.html              # Login + OTP UI
│       ├── student.html            # "Welcome, Student"
│       └── tutor_dashboard.html    # "Welcome, Tutor"
│
├── .gitignore
├── .env                            # (create this manually)
├── README.md
└── Requirements.txt
```

---

## 🔧 Installation Guide

```bash
git clone https://github.com/abdulrehmangulfaraz/modular-auth-core
cd modular-auth-core
python -m venv venv
source venv/bin/activate.ps1      # Windows: venv\Scripts\activate
pip install -r Requirements.txt
```

---

## ⚙️ Configuration

Create a `.env` file in the root folder:

```ini
DATABASE_URL=sqlite:///./auth.db
OTP_EXPIRY_MINUTES=5
USER_ROLES=student,tutor,admin
```

You can switch to PostgreSQL by updating `DATABASE_URL` accordingly.

---

## 🗃️ Database Initialization

```bash
python backend/init_db.py
```

This will create the database and necessary tables using SQLAlchemy.

---

## ▶️ Running the App

```bash
uvicorn backend.main:app --reload
```

Then open your browser at:
📍 [http://localhost:8000](http://localhost:8000)

---

## 📄 Notes

* 🔸 This project includes only basic dashboard templates with "Welcome" messages — no detailed dashboard logic.
* 🔸 Templates are meant as placeholders and can be replaced or extended easily.
* 🔸 File uploads (e.g., CNIC, CVs) are supported but not actively used in dashboards yet.
* 🔸 OTP logic is functional (send, verify, resend) but assumes valid SMTP credentials in place.

---

## 📬 Contact

**Abdulrehman Gulfaraz**
<br> 📧 [abdulrehmangulfaraz@gmail.com](mailto:abdulrehmangulfaraz1@gmail.com) <br>
🐙 [github.com/abdulrehmangulfaraz](https://github.com/abdulrehmangulfaraz)<br>
💼 [linkedin.com/in/abdulrehman-gulfaraz](https://linkedin.com/in/abdulrehman-gulfaraz)

---

## 📜 License

Released under the [MIT License](LICENSE).
Feel free to use or modify this basic starter in your own FastAPI projects.

---

