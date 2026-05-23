<div align="center">

# 🎓 SCMS — Smart Campus Management System

**AI-Powered · Role-Based · Full-Stack Web App**

![Java](https://img.shields.io/badge/Java-17-orange?style=flat-square&logo=openjdk)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.2.3-6DB33F?style=flat-square&logo=springboot)
![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=flat-square&logo=mysql&logoColor=white)
![Thymeleaf](https://img.shields.io/badge/Thymeleaf-UI-005F0F?style=flat-square&logo=thymeleaf)
![Maven](https://img.shields.io/badge/Maven-Build-C71A36?style=flat-square&logo=apachemaven)

A centralized digital platform for colleges — managing students, attendance, exams, fees, placements, and analytics under one roof.

</div>

---

## 👨‍💻 Team — Group A

<div align="center">

| 👤 Member |
|:----------:|
| Vishwajit Gadale |
| Aakash Vishwakarma |
| Amar Bharati |

</div>

---

## ✨ Features by Role

<table>
<tr>
<td width="50%">

**🔴 Super Admin**
- Multi-college management
- Manage college-level admins
- Audit logs & communications
- Platform-wide notifications & reports

**🟠 Admin**
- Student & teacher registration
- Course, batch, subject, classroom management
- Smart timetable builder
- Fee structure & payment tracking
- Bulk import center & report export

</td>
<td width="50%">

**🟡 Teacher**
- Mark & manage attendance
- Create exams, enter marks, quiz results
- Upload assignments & study materials
- Timetable, subjects, student views

**🟢 Student**
- Dashboard — attendance, marks, exams
- Multi-step onboarding flow
- Fee portal, exam results, placements
- Events, study materials, notifications

</td>
</tr>
<tr>
<td>

**🔵 Placement (TPO)**
- Manage drives, companies & interviews
- Track applications & analytics
- Announcements to students

</td>
<td>

**🤖 Chatbot**
- AI-powered campus assistant
- Available in Student & Teacher dashboards

</td>
</tr>
</table>

---

## 🛠️ Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Java 17 |
| Framework | Spring Boot 3.2.3 |
| Web / UI | Spring MVC + Thymeleaf |
| Security | Spring Security 6 (session-based, RBAC) |
| Database | MySQL 8 + Spring Data JPA / Hibernate |
| Email | Spring Mail |
| Reports | Apache POI (Excel) · Apache PDFBox (PDF) |
| Build | Maven |
| Dev | Spring DevTools (live reload) |

---

## 📁 Project Structure

```
scms-project/
├── src/main/java/com/scms/scms/
│   ├── ScmsBackendApplication.java     ← Entry point
│   ├── config/                          ← Security, migrations, interceptors
│   ├── controller/                      ← Admin, Teacher, Student, SuperAdmin,
│   │                                       Placement, Chatbot controllers
│   ├── model/                           ← JPA Entities
│   ├── repository/                      ← Spring Data JPA Repositories
│   ├── service/                         ← Business logic, ExamAutomation, Chatbot
│   └── security/                        ← Field encryption (Aadhaar, PAN, bank)
│
├── src/main/resources/
│   ├── application.properties
│   ├── static/                          ← CSS, JS, images
│   └── templates/
│       ├── admin/                       ← Admin portal
│       ├── teacher/                     ← Teacher portal
│       ├── student/connected/           ← Student portal + onboarding
│       ├── placement/                   ← TPO portal
│       ├── super-admin/                 ← Super Admin portal
│       └── home/                        ← Public landing pages
│
├── scms_complete_database.sql           ← Full schema + seed data
└── pom.xml
```

---

## ⚙️ Getting Started

### Prerequisites
- Java 17+
- MySQL 8+
- Maven 3.8+

### 1. Clone
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
```properties
server.port=8082
spring.datasource.url=jdbc:mysql://localhost:3306/scms
spring.datasource.username=root
spring.datasource.password=YOUR_PASSWORD_HERE
```
> ⚠️ Never commit real credentials. Add `application.properties` to `.gitignore`.

### 4. Run
```bash
mvn clean install
mvn spring-boot:run
```

> App runs at **http://localhost:8082**

---

## 🔐 Security

- Passwords hashed with **BCrypt**
- Sensitive fields (Aadhaar, PAN, bank details) **field-encrypted** at DB level
- Set encryption key as environment variable:
  ```bash
  export FIELD_ENCRYPTION_SECRET=your_strong_secret_here
  ```
- Spring Security 6 — each portal is fully isolated by role

---

## 📦 Key Dependencies

| Dependency | Purpose |
|-----------|---------|
| `spring-boot-starter-security` | Auth & authorization |
| `spring-boot-starter-thymeleaf` | Server-side HTML templates |
| `spring-boot-starter-mail` | Email notifications |
| `poi-ooxml` | Excel export |
| `pdfbox` | PDF generation |
| `mysql-connector-j` | MySQL driver |
| `spring-boot-devtools` | Hot reload |

---

<div align="center">

**Developed for academic purposes — Java Full Stack Internship Project**

</div>
