# 🏥 Hospital Management System

> A GUI-based desktop application to manage hospital records, appointments, and billing using Python and Tkinter.

![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Tkinter](https://img.shields.io/badge/Tkinter-GUI-orange?style=for-the-badge)
![SQLite](https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white)

---

## 📌 Overview

The **Hospital Management System** is a desktop application that simplifies hospital administration. It manages patient records, doctor schedules, appointments, and billing — all through an intuitive GUI built with Python's Tkinter library.

---

## ✨ Features

- 👤 **Patient Management** — Register, update, search, and delete patient records
- 🩺 **Doctor Management** — Maintain doctor profiles, specializations, and schedules
- 📅 **Appointment Booking** — Schedule, reschedule, and cancel appointments
- 🧾 **Billing System** — Generate bills with itemized treatment charges
- 🔍 **Search & Filter** — Quick search by patient ID, name, or date
- 🗃️ **Database Storage** — Persistent local database with SQLite

---

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| Language | Python 3.8+ |
| GUI Framework | Tkinter |
| Database | SQLite3 |
| ORM | sqlite3 (built-in) |

---

## 🚀 Getting Started

### Prerequisites

```bash
Python 3.8+
# Tkinter comes pre-installed with Python
# No extra pip installs required for basic setup
```

### Installation

```bash
# 1. Clone the repository
git clone https://github.com/Gangadhar-tech-coder/Hospital-Management.git
cd Hospital-Management

# 2. Run the application
python main.py
```

---

## 📁 Project Structure

```
Hospital-Management/
├── main.py               # Entry point — launches main window
├── database.py           # SQLite connection and queries
├── patients.py           # Patient CRUD operations
├── doctors.py            # Doctor management
├── appointments.py       # Appointment scheduling
├── billing.py            # Bill generation
├── ui/
│   ├── patient_form.py   # Patient registration UI
│   ├── doctor_form.py    # Doctor management UI
│   ├── appointment_ui.py # Appointment booking UI
│   └── billing_ui.py     # Billing UI
├── hospital.db           # SQLite database (auto-created)
└── README.md
```

---

## 🗄️ Database Schema

```sql
-- Patients table
CREATE TABLE patients (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    age INTEGER,
    gender TEXT,
    phone TEXT,
    address TEXT,
    blood_group TEXT,
    registered_on DATE
);

-- Doctors table
CREATE TABLE doctors (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    name TEXT NOT NULL,
    specialization TEXT,
    phone TEXT,
    available_days TEXT
);

-- Appointments table
CREATE TABLE appointments (
    id INTEGER PRIMARY KEY AUTOINCREMENT,
    patient_id INTEGER,
    doctor_id INTEGER,
    date DATE,
    time TIME,
    status TEXT DEFAULT 'Scheduled',
    FOREIGN KEY (patient_id) REFERENCES patients(id),
    FOREIGN KEY (doctor_id) REFERENCES doctors(id)
);
```

---

## 💡 Usage

1. Launch the app: `python main.py`
2. **Register a Patient** → Go to Patients tab → Fill form → Save
3. **Add a Doctor** → Go to Doctors tab → Add specialization and schedule
4. **Book Appointment** → Appointments tab → Select patient + doctor + slot
5. **Generate Bill** → Billing tab → Select patient → Add services → Generate

---

