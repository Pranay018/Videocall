# Execution Flow — Video Call Application

## 1. App Startup
- User loads frontend (Netlify)
- React initializes AuthContext
- If JWT exists → user auto-logged in
- Landing page or login loads

---

## 2. Authentication Flow
1. User submits login credentials  
2. Frontend sends:
```
POST /api/auth/login
```
3. Backend verifies user  
4. Returns JWT + user  
5. Stored in localStorage and context  

---

## 3. Starting a Video Call (WebRTC)
1. User selects “Start Call”  
2. Frontend connects to signaling server (Socket.io)
```
socket.emit("join-room", roomId)
```
3. WebRTC peer connection created  
4. User media stream (camera/mic) requested  
5. Signaling exchange:
   - offer  
   - answer  
   - ICE candidates  
6. Remote peer connected → video streams display  

---

## 4. Ending a Call
- User clicks “End”
- Peer connection closes
- Backend stores call history:
```
POST /api/history
```

---

## 5. Viewing Call History
Frontend sends:
```
GET /api/history
```
Backend returns past call sessions.

