# Smart Student Hub - User Flow

## Complete User Journey

### 🎯 Landing Page (index.html)
**Entry point for all users**
- Overview of system features
- Two options:
  - "Login to Your Account" → Goes to login.html
  - "Create Faculty Account" → Goes to faculty-register.html

---

## Faculty Journey

### 1️⃣ Faculty Registration (faculty-register.html)
**First-time faculty users**
- Fill registration form:
  - Full Name
  - Email Address
  - Department (optional)
  - Password
  - Confirm Password
- Submit → Account created
- Redirect to login page

### 2️⃣ Faculty Login (login.html)
- Select "Faculty" role
- Enter:
  - Email Address
  - Password
- Submit → Redirects to Faculty Panel

### 3️⃣ Faculty Panel (faculty-panel.html)
**Faculty Dashboard with multiple sections:**

#### A. Register Student
- Add new students with:
  - Full Name
  - USN (University Seat Number)
  - Email
  - Department
  - Semester
  - Date of Birth
  - Default Password (backup)
- Student receives USN + DOB as login credentials

#### B. Mark Attendance
- Enter student USN or email
- Select subject, date, status (Present/Absent/Late)
- Add remarks (optional)
- Submit attendance record

#### C. Enter Marks
- Enter student USN or email
- Select subject, exam type
- Enter marks obtained and total marks
- Add date and remarks
- Submit marks record

#### D. Add Extracurricular Activity
- Enter student USN or email
- Add activity details:
  - Title
  - Type (Sports/Cultural/Competition/Workshop/etc.)
  - Description
  - Date
  - Remarks
- Activity is auto-approved (faculty-added)

---

## Student Journey

### 1️⃣ Student Registration
**Students CANNOT self-register**
- Must be registered by faculty through Faculty Panel
- Faculty provides:
  - USN
  - Date of Birth
- These become the student's login credentials

### 2️⃣ Student Login (login.html)
- Select "Student" role
- Enter:
  - USN (University Seat Number)
  - Date of Birth
- Submit → Redirects to Student Dashboard

### 3️⃣ Student Dashboard (dashboard.html)
**Student Dashboard with multiple sections:**

#### A. Overview
- View statistics:
  - Attendance Rate (%)
  - Average Marks (%)
  - Total Activities
- Quick summary of performance

#### B. Attendance Records
- View all attendance records
- Filter by subject and date
- See status (Present/Absent/Late)
- View faculty remarks

#### C. Marks
- View all exam marks
- See subject-wise performance
- View percentages and grades
- Track progress over time

#### D. Activities
- View all extracurricular activities
- See activity type and status
- Read descriptions and remarks
- Track participation

#### E. Projects
- Add new projects:
  - Title
  - Description
  - Tech Stack
  - Project Link
  - Status (Completed/In Progress/Planned)
- View all added projects
- Edit project details

#### F. Portfolio
- Generate professional portfolio
- Includes:
  - Personal Information & USN
  - Academic Performance (Marks & Attendance)
  - Projects with descriptions
  - Extracurricular Activities
  - Skills & Certifications
- Download as HTML document
- Use for placements, fellowships, admissions

---

## Authentication Flow

```
┌─────────────────┐
│  Landing Page   │
│  (index.html)   │
└────────┬────────┘
         │
    ┌────┴────┐
    │         │
    ▼         ▼
┌────────┐  ┌──────────────────┐
│ Login  │  │ Faculty Register │
└───┬────┘  └────────┬─────────┘
    │                │
    │                ▼
    │         ┌──────────────┐
    │         │ Registration │
    │         │   Success    │
    │         └──────┬───────┘
    │                │
    └────────┬───────┘
             │
      ┌──────┴──────┐
      │             │
      ▼             ▼
┌──────────┐  ┌──────────────┐
│ Student  │  │   Faculty    │
│Dashboard │  │    Panel     │
└──────────┘  └──────────────┘
```

---

## Key Features

### ✅ Role-Based Access Control
- **Faculty**: Can register students, manage records, view all data
- **Students**: Can only view their own data, add projects, generate portfolio

### ✅ Secure Authentication
- **Students**: Login with USN + Date of Birth (no password needed)
- **Faculty**: Login with Email + Password
- JWT tokens for session management
- Password hashing with bcrypt

### ✅ Data Management
- Faculty can add/update student records
- Students can view and download their data
- Real-time statistics and analytics
- Portfolio generation for career opportunities

### ✅ User-Friendly Interface
- Modern, responsive design
- Clear role selection
- Intuitive navigation
- Error handling and validation

---

## System Requirements

- **Backend**: Node.js server running on port 5000
- **Database**: MongoDB running locally
- **Frontend**: Modern web browser (Chrome, Firefox, Safari, Edge)
- **Network**: Internet connection for API calls

---

## Quick Start Guide

### For Faculty (First Time)
1. Open `web/index.html` or `web/faculty-register.html`
2. Create your faculty account
3. Login with your credentials
4. Start registering students

### For Students
1. Wait for faculty to register you
2. Receive your USN and Date of Birth
3. Open `web/login.html`
4. Login with USN + DOB
5. Access your dashboard

---

## Support & Troubleshooting

### Common Issues

**"Unable to connect to server"**
- Ensure backend server is running: `npm start` in backend folder
- Check MongoDB is running
- Verify port 5000 is not blocked

**"Invalid credentials"**
- Students: Verify USN and DOB with faculty
- Faculty: Check email and password
- Ensure you selected the correct role

**"Student not found"**
- Faculty must register the student first
- Verify USN is entered correctly (case-sensitive)
- Check student exists in database

---

## Contact & Support

For technical issues or questions:
- Contact your institution's IT department
- Check system documentation
- Report bugs to development team
