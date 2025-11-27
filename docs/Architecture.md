# Architecture — Video Call Application (Full Stack)

## Overview
This project is a **full‑stack video calling platform** built using:
- **Frontend:** React (Create React App)
- **Backend:** Node.js + Express + MongoDB
- **Authentication:** JWT
- **Video Calls:** WebRTC + Socket.io signaling
- **Deployment:**  
  - Frontend → Netlify  
  - Backend → Render

## High-Level Architecture
```
                           +-------------------+
                           |       Users       |
                           +---------+---------+
                                     |
                                     | HTTPS + WebSockets
                                     |
                           +---------v---------+
                           |     Frontend      |  React
                           | - WebRTC UI       |
                           | - Auth UI         |
                           | - Socket client   |
                           +---------+---------+
                                     |
                                     | REST + WS
                                     |
                           +---------v---------+
                           |      Backend      | Node.js
                           | - Auth API        |
                           | - Signaling       |
                           | - Call history    |
                           | - JWT auth        |
                           +---------+---------+
                                     |
                                     | MongoDB
                                     |
                           +---------v---------+
                           |     Database      |
                           +-------------------+
```

## Key Modules

### Frontend
- `contexts/AuthContext.jsx` — manages authentication state  
- `VideoMeet.jsx` — video call screen using WebRTC  
- `withAuth.jsx` — route protection  
- `pages/landing.jsx` — landing page  
- `pages/history.jsx` — call history  

### Backend
- `controllers/*` — login, register, call history  
- `routes/*` — authentication + video call endpoints  
- `middleware/auth.js` — verifies JWT  
- Socket.io server for signaling  

