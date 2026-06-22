# 🎓 Smart Student Hub

A centralized student management platform that helps educational institutions manage student records, academic performance, projects, achievements, attendance, and portfolio generation in one place.

## 🚀 Features

### 👨‍🎓 Student Module
- Student Login using USN and Date of Birth
- View Attendance Records
- View Academic Marks and Performance
- Manage Personal Projects
- Track Achievements and Activities
- Interactive Student Dashboard
- Generate Professional Portfolio

### 👨‍🏫 Faculty Module
- Faculty Registration and Login
- Register New Students
- Manage Student Records
- Mark Attendance
- Enter Academic Marks
- Add Extracurricular Activities
- View Student Achievements

### 📊 Dashboard & Analytics
- Attendance Statistics
- Academic Performance Overview
- Activity Tracking
- Achievement Monitoring
- Portfolio Completion Status
- Performance Insights

### 🏆 Achievement Management
- Internships
- Workshops
- Online Courses
- Certifications
- Hackathons
- Academic Achievements
- Extracurricular Activities

### 📄 Portfolio Generator
- Automatic Portfolio Creation
- Academic Records Integration
- Project Showcase
- Skills Summary
- Achievement Highlights
- Downloadable Portfolio

---

## 🛠️ Tech Stack

### Frontend
- HTML5
- CSS3
- JavaScript

### Backend
- Node.js
- Express.js

### Database
- MongoDB

### Authentication
- JWT Authentication

### Additional Tools
- PDFKit
- Nodemon

---

## 📂 Project Structure

```text
SmartStudentHub/
│
├── backend/
├── web/
├── scripts/
├── mobile/
├── server.js
├── package.json
└── README.md
```

---

## 🔐 Authentication

### Student Login
- USN
- Date of Birth

### Faculty Login
- Email
- Password

Secure JWT-based authentication is implemented for role-based access control. :contentReference[oaicite:0]{index=0}

---

## 📈 Key Functionalities

- Student Record Management
- Attendance Tracking
- Marks Management
- Project Management
- Achievement Tracking
- Faculty Monitoring
- Portfolio Generation
- Dashboard Analytics

The platform provides a complete digital solution for managing student academic and professional development. :contentReference[oaicite:1]{index=1} :contentReference[oaicite:2]{index=2}

---

## 🎯 Future Enhancements

- AI-Based Career Recommendations
- Placement Tracking
- Resume Builder
- Mobile Application
- Advanced Analytics Dashboard
- Notification System

---

## 👨‍💻 Author

**Uluru Phani Kumar**

B.E - CSE (Data Science)

Ballari Institute of Technology and Management

GitHub: https://github.com/Phani153

---

## ⭐ Project Goal

To provide a centralized platform that streamlines student academic management, achievement tracking, faculty monitoring, and portfolio generation while reducing manual record maintenance.


## Installation

1. Clone the repository
git clone <repository-url>

2. Install dependencies
npm install

3. Configure environment variables
Create a .env file and add:

PORT=5500
MONGO_URI=mongodb://127.0.0.1:27017/smarthub
JWT_SECRET=your_secret_key

4. Run the project
npm run dev
