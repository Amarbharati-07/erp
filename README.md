# 🎓 AI-Powered Smart Campus Management System (SCMS)

A centralized digital platform for colleges to manage students, attendance, assignments, fees, exams, and analytics — with role-based access and AI-driven insights.

> **Group A** | Java Full Stack Project
> 
> | Member | Responsibility |
> |--------|---------------|
> | Vishwajit Gadale | Backend APIs + Security |
> | Akash Vishwakarma | Exam + Fee + Analytics Logic |
> | Amar Bharati | Frontend Dashboard + Charts + UI + Integration |

---

## 📌 Project Overview

SCMS is **not** a simple CMS. It combines academic management with **AI-based analytics and automation** to help colleges:

- Automate attendance and academic tracking
- Identify at-risk students early
- Provide real-time data-driven insights
- Reduce paperwork and manual workloads
- Centralize all institutional data

---

## 🚀 Key Features

### 👨‍🎓 Student Module
- Attendance tracking & reports
- Subject-wise performance view
- Fee payment portal
- In-app & email notifications

### 👨‍🏫 Faculty Module
- Mark attendance
- Upload assignments
- Enter internal/external marks
- Generate class performance reports

### 🛡️ Admin Module
- Role management (Admin, Faculty, Student)
- Student analytics dashboard
- Dropout / at-risk prediction (ML-based)
- Export reports as PDF / Excel

### 🤖 AI Analytics Module
- Performance prediction using historical marks
- Attendance risk alert system
- Performance heatmaps on dashboard
- Faculty alerts for weak students

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Backend | Java 17+, Spring Boot, Spring Security, Hibernate/JPA, Maven, Lombok |
| Database | MySQL (normalized schema, indexed on student_id, course_id, exam_id) |
| Frontend | React.js, Axios, React Router, Context API / Redux, Chart.js / Recharts, Material UI / Tailwind CSS |
| Auth | JWT Authentication + RBAC |
| AI Component | Python microservice (optional) or Java-based statistical model |
| DevOps | Docker, GitHub, Postman, Swagger, CI/CD (optional) |

---

## 🏗️ Architecture

### Option 1 – Monolithic (Default)
Single Spring Boot application with well-organized modules.

### Option 2 – Microservices (Enterprise)
```
Auth Service → Student Service → Attendance Service
     ↓               ↓                  ↓
Exam Service → Analytics Service → Notification Service
                     ↓
               API Gateway
```

---

## 🗄️ Database Schema (Core Tables)

```
users, roles, students, faculty, courses, subjects,
attendance, exams, marks, fees, payments,
notifications, analytics_logs
```

---

## 📋 Functional Requirements Summary

| Module | Key Requirements |
|--------|-----------------|
| User Management | Registration, role-based login, password reset |
| Student Management | Profile CRUD, academic history, enrollment status |
| Attendance | Mark attendance, % calculation, threshold alerts |
| Exams & Results | Marks entry, GPA/CGPA calculation, result sheets |
| Fee Management | Fee structure, payment records, receipt generation |
| AI Analytics | Performance trends, at-risk prediction, heatmaps |
| Notifications | In-app, email, broadcast announcements |
| Reports | PDF/Excel export, consolidated dashboards |

---

## ⚙️ Non-Functional Requirements

- **Performance:** 1000 concurrent users, API response < 2s
- **Security:** BCrypt passwords, JWT auth, SQL injection prevention, CSRF protection
- **Scalability:** Horizontal scaling, modular architecture
- **Reliability:** 99% uptime, data backup mechanism
- **Maintainability:** Clean architecture, SLF4J logging, Swagger API docs

---

## 📁 Project Structure

```
scms/
├── backend/
│   ├── src/main/java/com/scms/
│   │   ├── auth/
│   │   ├── student/
│   │   ├── attendance/
│   │   ├── exam/
│   │   ├── fee/
│   │   ├── analytics/
│   │   └── notification/
│   └── pom.xml
├── frontend/
│   ├── src/
│   │   ├── components/
│   │   ├── pages/
│   │   ├── context/
│   │   └── services/
│   └── package.json
├── database/
│   └── schema.sql
├── docs/
│   ├── BRS.md
│   └── SRS.md
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites
- Java 17+
- Node.js 18+
- MySQL 8+
- Maven
- Docker (optional)

### Backend Setup
```bash
cd backend
# Configure DB credentials in application.properties
mvn clean install
mvn spring-boot:run
```

### Frontend Setup
```bash
cd frontend
npm install
npm start
```

### Database Setup
```bash
mysql -u root -p < database/schema.sql
```

### API Documentation
Once the backend is running, visit:
```
http://localhost:8080/swagger-ui.html
```

---

## 👥 Stakeholders

- College Management / Principal / Director
- Faculty Members
- Students & Parents
- Admin Staff / IT Administrator

---

## 📄 License

This project is developed for academic purposes as part of a Java Full Stack internship project.
