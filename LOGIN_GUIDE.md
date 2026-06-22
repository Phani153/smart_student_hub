# Smart Student Hub - Login Guide

## Overview
The Smart Student Hub uses a role-based authentication system with different login methods for students and faculty.

## Login Methods

### For Students
**Login Credentials:**
- **USN (University Seat Number)**: Provided by the college during registration
- **Date of Birth**: Your date of birth as registered by faculty

**Steps:**
1. Go to the login page
2. Click on "Student" role
3. Enter your USN (e.g., 1MS21CS001)
4. Enter your Date of Birth
5. Click "Login as Student"

**Note:** Students do NOT need a password. Authentication is done using USN + Date of Birth for security.

### For Faculty
**Login Credentials:**
- **Email**: Your registered email address
- **Password**: Your account password

**Steps:**
1. Go to the login page
2. Click on "Faculty" role
3. Enter your email address
4. Enter your password
5. Click "Login as Faculty"

## Student Registration Process

Students cannot self-register. Faculty members must register students through the Faculty Panel:

1. Faculty logs in to their account
2. Navigate to "Register Student" section
3. Fill in student details:
   - Full Name
   - USN (University Seat Number)
   - Email
   - Department
   - Semester
   - Date of Birth
   - Default Password (for backup access)
4. Click "Register Student"
5. Share the USN and Date of Birth with the student

## Faculty Registration

Faculty members can create their own accounts through the Faculty Registration page.

**To create a faculty account:**
1. Go to the landing page or login page
2. Click on "Create Faculty Account" or "Register as Faculty"
3. Fill in the registration form:
   - Full Name
   - Email Address
   - Department (optional)
   - Password (minimum 6 characters)
   - Confirm Password
4. Click "Create Faculty Account"
5. After successful registration, you'll be redirected to the login page

**Note:** Only faculty can register themselves. Students CANNOT self-register and must be registered by faculty members.

## Security Features

- **Students**: Login with USN + Date of Birth (no password needed for daily use)
- **Faculty**: Login with Email + Password
- **Role-based Access**: Students can only view their own data, Faculty can manage all students
- **JWT Tokens**: Secure token-based authentication with 7-day expiry
- **Password Hashing**: All passwords are hashed using bcrypt

## API Endpoints

### Authentication
- `POST /api/auth/login-student` - Student login (USN + DOB)
- `POST /api/auth/login-faculty` - Faculty login (Email + Password)
- `POST /api/auth/register-student` - Register new student (Faculty only)
- `POST /api/auth/register` - Register faculty/admin

### Student Features
- View attendance records
- View marks and grades
- View extracurricular activities
- Add and manage projects
- Generate and download portfolio

### Faculty Features
- Register new students
- Mark attendance
- Enter marks
- Add extracurricular activities
- View all student records

## Troubleshooting

### "Missing credentials" error
- Make sure you've selected a role (Student or Faculty)
- Ensure all required fields are filled
- Check that the backend server is running

### "Invalid credentials" error
**For Students:**
- Verify your USN is correct (check with faculty)
- Ensure Date of Birth matches what was registered
- Contact faculty if you haven't been registered yet

**For Faculty:**
- Check your email address is correct
- Verify your password
- Contact administrator if you need to reset password

### Cannot connect to server
- Ensure backend server is running on `http://localhost:5000`
- Check your internet connection
- Verify MongoDB is running

## System Requirements

- Modern web browser (Chrome, Firefox, Safari, Edge)
- Backend server running on Node.js
- MongoDB database
- Internet connection

## Support

For technical issues or questions:
- Contact your institution's IT department
- Check the system documentation
- Report bugs to the development team
