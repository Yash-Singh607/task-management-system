# Task Management System

College project — Admin/Manager assigns tasks to employees.

**Stack:** HTML, CSS, JavaScript, Python (Flask), MySQL

## Features

- Login with Admin / Manager roles
- Assign tasks to employees (search, add new employee inline)
- Task CRUD with MySQL backend
- Employee directory and reports dashboard
- Professional UI (TaskFlow)

## Setup

### 1. Install dependencies

```powershell
pip install -r requirements.txt
```

### 2. Configure MySQL

Copy `.env.example` to `.env` and set your MySQL connection:

```env
MYSQL_HOST=127.0.0.1
MYSQL_PORT=3307
MYSQL_USER=root
MYSQL_PASSWORD=
MYSQL_DATABASE=task_management
```

> **XAMPP users:** If MySQL 8.0 uses port 3306, run XAMPP MariaDB on port 3307 (see project docs) or stop the MySQL80 service.

### 3. Start MySQL and initialize database

```powershell
python setup_db.py
```

### 4. Run the app

```powershell
python app.py
```

Open **http://127.0.0.1:5000**

## Login credentials

| Username | Password   | Role    |
|----------|------------|---------|
| admin    | admin123   | Admin   |
| manager  | manager123 | Manager |

## Project structure

```
task-management-system/
├── app.py              # Flask routes & API
├── config.py           # Settings (.env support)
├── db.py               # MySQL connection
├── setup_db.py         # Database setup & seed
├── database/
│   ├── schema.sql      # MySQL schema
│   └── employee_names.py
├── templates/          # HTML pages
├── static/             # CSS, JS, images
└── requirements.txt
```

## Database schema

- `login_table` — Admin/Manager authentication
- `employees` — Employee master (FK source)
- `tasks` — Tasks linked to employees via `employee_id`
