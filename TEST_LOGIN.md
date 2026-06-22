# Student Login Troubleshooting Guide

## Issue: Unable to Login as Student

### Common Causes:

1. **Student Not Registered Yet**
   - Students must be registered by faculty first
   - Faculty needs to provide USN and Date of Birth during registration

2. **Incorrect USN Format**
   - USN should be in uppercase (auto-converted)
   - Example: 1MS21CS001

3. **Date of Birth Mismatch**
   - Must match exactly what faculty entered
   - Format: YYYY-MM-DD

4. **Backend Server Not Running**
   - Check if server is running on port 5000
   - Look for "Server running on port 5000" message

---

## Step-by-Step Testing:

### Step 1: Register a Test Student (Faculty)

1. **Login as Faculty:**
   - Go to `faculty-register.html`
   - Create a faculty account if you don't have one
   - Email: `test@faculty.com`
   - Password: `password123`

2. **Register a Student:**
   - Login to Faculty Panel
   - Go to "Register Student" section
   - Fill in:
     - Name: `Test Student`
     - USN: `1MS21CS001`
     - Email: `student@test.com`
     - Department: `Computer Science`
     - Semester: `5`
     - Date of Birth: `2003-01-15` (or any date you'll remember)
     - Password: `student123` (backup, not used for login)
   - Click "Register Student"

### Step 2: Test Student Login

1. **Go to Login Page:**
   - Open `login.html`

2. **Select Student Role:**
   - Click on "Student" button

3. **Enter Credentials:**
   - USN: `1MS21CS001`
   - Date of Birth: `2003-01-15` (same as registered)

4. **Click Login:**
   - Should redirect to dashboard
   - If error, check console (F12)

---

## Debugging Steps:

### Check Backend Server:

```bash
# In backend folder
npm start
```

Expected output:
```
Server running on port 5000
✅ MongoDB connected
```

### Check Browser Console:

1. Open browser DevTools (F12)
2. Go to Console tab
3. Try logging in
4. Look for error messages

### Common Error Messages:

**"Invalid credentials"**
- USN doesn't exist in database
- Date of Birth doesn't match
- Solution: Re-register student or check DOB

**"Unable to connect to server"**
- Backend not running
- Wrong port
- Solution: Start backend server

**"Date of Birth not set"**
- Student registered without DOB
- Solution: Re-register student with DOB

---

## Test API Directly:

### Test Student Registration:

```javascript
// In browser console (after faculty login)
const token = localStorage.getItem('token');

fetch('http://localhost:5000/api/auth/register-student', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json',
    'Authorization': `Bearer ${token}`
  },
  body: JSON.stringify({
    name: 'Test Student',
    usn: '1MS21CS001',
    email: 'student@test.com',
    department: 'Computer Science',
    semester: 5,
    dateOfBirth: '2003-01-15',
    password: 'student123'
  })
})
.then(r => r.json())
.then(console.log);
```

### Test Student Login:

```javascript
// In browser console
fetch('http://localhost:5000/api/auth/login-student', {
  method: 'POST',
  headers: {
    'Content-Type': 'application/json'
  },
  body: JSON.stringify({
    usn: '1MS21CS001',
    dateOfBirth: '2003-01-15'
  })
})
.then(r => r.json())
.then(console.log);
```

Expected response:
```json
{
  "message": "Logged in successfully",
  "token": "eyJhbGc...",
  "user": {
    "id": "...",
    "name": "Test Student",
    "email": "student@test.com",
    "usn": "1MS21CS001",
    "role": "student",
    "department": "Computer Science",
    "semester": 5
  }
}
```

---

## Quick Fix Checklist:

- [ ] Backend server is running
- [ ] MongoDB is connected
- [ ] Faculty account exists
- [ ] Student is registered with USN and DOB
- [ ] USN is correct (uppercase)
- [ ] Date of Birth matches exactly
- [ ] Browser console shows no errors
- [ ] Network tab shows API calls

---

## If Still Not Working:

### Check Database:

1. Open MongoDB Compass or mongo shell
2. Connect to `mongodb://127.0.0.1:27017/smarthub`
3. Check `users` collection
4. Find student by USN
5. Verify `dateOfBirth` field exists

### Reset and Try Again:

1. Delete student from database
2. Re-register through faculty panel
3. Note down exact USN and DOB
4. Try login again

---

## Contact Support:

If issue persists:
1. Check backend logs
2. Check browser console errors
3. Verify API endpoints are working
4. Check network requests in DevTools

---

## Marks Entry - Date Field Removed

The date field has been removed from the marks entry form. The system now automatically uses the current date when marks are entered.

**Changes Made:**
- ✅ Removed date input field from marks form
- ✅ Auto-set date to current date when saving marks
- ✅ Simplified marks entry process

**Faculty can now:**
1. Search for student
2. Enter number of subjects
3. Fill in subject details (name, exam type, marks)
4. Save all marks at once
5. Date is automatically recorded as today

---

**Remember:** Students can only login after being registered by faculty with USN and Date of Birth!
