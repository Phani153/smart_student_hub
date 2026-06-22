# Server Setup Guide - Smart Student Hub

## ✅ Backend is Now Connected to Serve Frontend

Your backend server is now configured to serve both the API and the frontend files from a single server.

## 🚀 How to Access the Application

### Start the Server
```bash
cd backend
npm start
```

### Access URLs
Once the server is running, you can access:

- **Main Application**: http://localhost:5000/
- **Login Page**: http://localhost:5000/login.html
- **Student Dashboard**: http://localhost:5000/dashboard.html
- **Faculty Panel**: http://localhost:5000/faculty-panel.html
- **Admin Panel**: http://localhost:5000/admin-panel.html
- **API Endpoint**: http://localhost:5000/api/

## 📁 What Changed

The backend now serves static files from the `web` directory:
- All HTML, CSS, and JavaScript files are accessible
- API routes are available at `/api/*`
- No need to run a separate frontend server

## 🔧 Configuration

### Backend (backend/src/app.js)
```javascript
// Serves static files from web directory
app.use(express.static(path.join(__dirname, '../../web')));

// API routes
app.use('/api/auth', authRoutes);
app.use('/api/profile', profileRoutes);
// ... other routes
```

### Environment Variables (backend/.env)
```
MONGO_URI=mongodb://127.0.0.1:27017/smarthub
JWT_SECRET=smartstudenthubsecretkey
PORT=5000
```

## 🎯 Quick Start Steps

1. **Ensure MongoDB is Running**
   ```bash
   # Check if MongoDB is running
   tasklist | findstr mongod
   ```

2. **Start the Backend Server**
   ```bash
   cd backend
   npm start
   ```

3. **Open Your Browser**
   - Navigate to: http://localhost:5000/
   - You should see the Smart Student Hub homepage

## 👥 Login Credentials

### Student Login
- **USN**: (Your registered USN)
- **Date of Birth**: (Your registered DOB)

### Faculty Login
- **Email**: faculty@example.com
- **Password**: (Your faculty password)

### Admin Login
- **Email**: admin@example.com
- **Password**: (Your admin password)

## 🛠️ Troubleshooting

### Port Already in Use
If you see "EADDRINUSE" error:
```bash
# Find process using port 5000
netstat -ano | findstr :5000

# Kill the process (replace PID with actual process ID)
taskkill /PID <PID> /F
```

### MongoDB Not Connected
- Ensure MongoDB service is running
- Check connection string in backend/.env
- Verify MongoDB is listening on port 27017

### Cannot Access Frontend
- Verify server is running: http://localhost:5000/
- Check browser console for errors (F12)
- Ensure all files are in the `web` directory

## 📊 Server Status Check

To verify everything is working:

1. **Server Running**: Look for "Server running on port 5000"
2. **MongoDB Connected**: Look for "✅ MongoDB connected"
3. **Test API**: Visit http://localhost:5000/api/
4. **Test Frontend**: Visit http://localhost:5000/

## 🔄 Restart Server

If you make changes to backend code:
```bash
# Stop the server (Ctrl+C in terminal)
# Then restart
npm start
```

## 📝 Notes

- Frontend files are served from the `web` directory
- API endpoints are prefixed with `/api/`
- All routes work from a single port (5000)
- CORS is enabled for development
- Static files (CSS, JS, images) are automatically served

## 🎉 You're All Set!

Your Smart Student Hub is now running with:
- ✅ Backend API on port 5000
- ✅ Frontend served from the same port
- ✅ MongoDB connected
- ✅ All features accessible from http://localhost:5000/

Enjoy using Smart Student Hub! 🚀
