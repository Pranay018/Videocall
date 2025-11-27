# Deployment — Netlify (Frontend) & Render (Backend)

## Backend Environment Variables (Render)
Add these in Render → Environment:
```
PORT=5000
MONGO_URI=your-mongodb-url
JWT_SECRET=your-secret
ORIGIN_URL=https://your-frontend.netlify.app
```

---

# FRONTEND DEPLOYMENT — NETLIFY

## Step 1 — Build command
```
npm run build
```

## Step 2 — Publish directory
```
build
```

---

## Method 1: Deploy from GitHub
1. Push frontend folder to GitHub  
2. Go to Netlify → Add New Site → Import from Git  
3. Set:
   - Build command: `npm run build`
   - Publish directory: `build`
4. Add environment variable:
```
REACT_APP_API_URL=https://your-backend.onrender.com
```
5. Deploy.

---

## Method 2: Manual upload
```
npm run build
```
Upload the **build** folder to Netlify.

---

# BACKEND DEPLOYMENT — RENDER

## Step 1 — Create Web Service
- Environment: **Node**
- Build command:
```
npm install
```
- Start command:
```
node server.js
```

## Step 2 — Add Environment Variables
```
PORT=5000
MONGO_URI=your-mongodb-url
JWT_SECRET=your-secret
ORIGIN_URL=https://your-frontend.netlify.app
```

## Step 3 — Deploy
Render auto-builds and deploys.

Note: WebSockets are **enabled by default** on Render.

