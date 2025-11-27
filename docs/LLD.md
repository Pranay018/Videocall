# Low Level Design — Video Call Application

## Backend Structure
```
backend/
 ├── controllers/
 ├── middleware/
 ├── models/
 ├── routes/
 ├── server.js
 └── socket.js (if present)
```

### Models
**User**
- name  
- email  
- passwordHash  

**CallHistory**
- userId  
- peerId  
- duration  
- timestamp  

### Controllers
- authController → login/register  
- historyController → save/get call history  

### Middleware
- `auth.js` → verifies JWT token  

### WebRTC Signaling (Socket.io)
Events:
- `join-room`
- `offer`
- `answer`
- `ice-candidate`
- `call-ended`

---

## Frontend Structure
```
frontend/src/
 ├── contexts/
 ├── pages/
 ├── utils/
 ├── styles/
 └── index.js
```

### Important Components
**VideoMeet.jsx**
- Gets user media  
- Creates WebRTC connection  
- Sends signaling events through Socket.io  

**AuthContext.jsx**
- Holds JWT + user info  

**withAuth.jsx**
- Redirects unauthenticated users  

**history.jsx**
- Displays past calls  

