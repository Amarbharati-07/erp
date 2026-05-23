# 🎓 AI-Powered Smart Campus Management System (SCMS)

A full-stack web application built with **Spring Boot + Thymeleaf + MySQL** that centralizes college operations — student management, attendance, exams, fees, placements, and analytics — under one roof with role-based access control.

---

## 👨‍💻 Team — Group A

| Member |
|--------|
| Vishwajit Gadale |
| Akash Vishwakarma |
| Amar Bharati |

---

## 🚀 Features by Role

### 🔴 Super Admin
- Multi-college management (add, edit, view colleges)
- Manage college-level admins
- Audit logs & communications
- Platform-wide notifications & reports

### 🟠 Admin
- Student & teacher registration
- Course, batch, subject, classroom management
- Timetable builder (smart scheduling)
- Fee structure & payment tracking
- Import center (bulk data upload)
- Reports & document management

### 🟡 Teacher
- Mark & manage attendance
- Create exams, enter marks, view quiz results
- Upload assignments & study materials
- Timetable, subjects, student list views
- Notifications & profile management

### 🟢 Student
- Dashboard with attendance, marks, upcoming exams
- Onboarding flow (personal, address, education, documents, payment)
- Fee portal, exam results, study materials
- Placement portal (v2), events, notifications

### 🔵 Placement (TPO)
- Manage placement drives & companies
- Track applications & interviews
- Placement analytics & reports
- Announcements to students

### 🤖 Chatbot
- AI-powered campus chatbot (available in Student & Teacher dashboards only)

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Java 17 |
| Framework | Spring Boot 3.2.3 |
| Web / UI | Spring MVC + Thymeleaf (server-side rendering) |
| Security | Spring Security 6 (session-based, role-based) |
| Database | MySQL 8 + Spring Data JPA / Hibernate |
| Email | Spring Mail |
| Reports | Apache POI (Excel), Apache PDFBox (PDF) |
| Build Tool | Maven |
| Dev Tools | Spring DevTools (live reload) |

---

## 📁 Project Structure

```
scms-project/
├── src/
│   └── main/
│       ├── java/com/scms/scms/
│       │   ├── ScmsBackendApplication.java   ← Entry point
│       │   ├── config/                        ← Security, migrations, interceptors
│       │   ├── controller/                    ← AdminController, TeacherController,
│       │   │                                     StudentController, SuperAdminController,
│       │   │                                     PlacementController, ChatbotController...
│       │   ├── model/                         ← JPA Entities (Student, Teacher, Fees,
│       │   │                                     ExamSession, PlacementDrive, Timetable...)
│       │   ├── repository/                    ← Spring Data JPA Repositories
│       │   ├── service/                       ← Business logic, Chatbot, ExamAutomation
│       │   └── security/                      ← Field encryption (Aadhaar, PAN, bank details)
│       └── resources/
│           ├── application.properties
│           ├── static/                        ← CSS, JS, images
│           └── templates/
│               ├── admin/                     ← Admin portal pages
│               ├── teacher/                   ← Teacher portal pages
│               ├── student/connected/         ← Student portal pages + onboarding
│               ├── placement/                 ← TPO/Placement portal pages
│               ├── super-admin/               ← Super Admin portal pages
│               ├── home/                      ← Public landing pages
│               └── fragments/chatbot.html     ← Shared chatbot widget
├── scms_complete_database.sql                 ← Full DB schema + seed data
├── scms_db_updated.sql                        ← Latest DB migrations
└── pom.xml
```

---

## ⚙️ Getting Started

### Prerequisites
- Java 17+
- MySQL 8+
- Maven 3.8+

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/scms-project.git
cd scms-project
```

### 2. Setup Database
```bash
mysql -u root -p
```
```sql
CREATE DATABASE scms;
USE scms;
SOURCE scms_complete_database.sql;
```

### 3. Configure `application.properties`
Edit `src/main/resources/application.properties`:
```properties
server.port=8082

spring.datasource.url=jdbc:mysql://localhost:3306/scms
spring.datasource.username=root
spring.datasource.password=YOUR_PASSWORD_HERE
```

> ⚠️ **Never commit real credentials.** Use environment variables or a `.env` file in production.

### 4. Run the Application
```bash
mvn clean install
mvn spring-boot:run
```



---

## 🔐 Security Notes

- Passwords are hashed using **BCrypt**
- Sensitive fields (Aadhaar, PAN, bank details) are **field-encrypted** at DB level
- Set `FIELD_ENCRYPTION_SECRET` as an environment variable in production:
  ```bash
  export FIELD_ENCRYPTION_SECRET=your_strong_secret_here
  ```
- Role-based access enforced via Spring Security — each portal is isolated

---

## 🗄️ Key Database Tables

```
students         teachers         admin            colleges
courses          batches          subjects         subject_master
academic_structure  timetable     class_room
attendance_sessions  attendance_entries
exam_sessions    exam_quiz_questions  exam_quiz_attempts
fees             placement_drives  placement_applications
placement_interviews  campus_events  study_materials
portal_notifications  super_admin_audit_logs
```

---

## 📦 Notable Dependencies

| Dependency | Purpose |
|-----------|---------|
| `spring-boot-starter-security` | Authentication & authorization |
| `spring-boot-starter-thymeleaf` | Server-side HTML templates |
| `spring-boot-starter-mail` | Email notifications |
| `apache poi-ooxml` | Excel report generation |
| `apache pdfbox` | PDF generation |
| `mysql-connector-j` | MySQL driver |
| `spring-boot-devtools` | Hot reload during development |

---

## 📄 License

Developed for academic purposes — Java Full Stack Internship Project.
