# Video Call Application

A full-stack **real-time video calling platform** using WebRTC, React, Node.js, and Socket.io.  
Frontend hosted on **Netlify**, backend on **Render**.

---

# ✨ Features
- Real-time video conferencing (WebRTC)
- User authentication (JWT)
- Call history tracking
- Modern UI using React
- Socket.io real-time signaling
- Secure API communication

---

# 🚀 Tech Stack

## Frontend
- React (CRA)
- WebRTC
- Socket.io client
- Tailwind / CSS modules

## Backend
- Node.js + Express
- Socket.io server
- MongoDB
- JWT authentication

---

# 🔧 Environment Variables

### Backend (Render)
```
PORT=5000
MONGO_URI=your-mongodb-url
JWT_SECRET=your-secret
ORIGIN_URL=https://your-frontend.netlify.app
```

### Frontend (Netlify)
```
REACT_APP_API_URL=https://your-backend.onrender.com
```

---

# 🛠 Local Setup

## Backend
```
cd backend
npm install
npm run dev
```

## Frontend
```
cd frontend
npm install
npm start
```

---

# 🌐 Deployment
- Frontend → Netlify (build: `npm run build`, publish: `build`)
- Backend → Render (Node web service)

---

Prepared by **Pranay Patankar**.
