# 🛒 MERN eCommerce App

A full-stack eCommerce application built with MongoDB, Express.js, React, and Node.js. It supports user and admin flows, secure auth, orders, and payments.

---

## 🔍 Overview

This monorepo contains:
- `backend` (Express/MongoDB API)
- `frontend` (React app)

The React frontend uses the same backend API.

---

## 📂 Project Structure

```
Ecommers-MERN-main/
├─ backend/
│  ├─ config/
│  ├─ controllers/
│  ├─ middleware/
│  ├─ models/
│  ├─ routes/
│  ├─ utils/
│  ├─ seeder.js
│  └─ server.js (Express entry)
├─ frontend/            (React app)
│  └─ src/
├─ uploads/
└─ package.json         (root scripts)
```

---

## ✅ Prerequisites

- Node.js 18+ and npm
- MongoDB running locally (or a cloud URI)
- A terminal in the project root (`Ecommers-MERN-main`)

---

## 🚀 Key Features

### ✅ User
- Secure auth with JWT (httpOnly cookie)
- Browse products, cart, checkout, orders
- Password reset flow

### 🛠️ Admin
- Manage products, orders, and users
- Uploads and dashboards

---

## ⚙️ Tech Stack

- Backend: Node.js, Express.js, MongoDB, Mongoose, JWT, Nodemailer
- React Frontend: React, Redux Toolkit, RTK Query, React Router

---

## 🔧 Setup

1) Install dependencies (root will install root deps only)

```
npm install
cd frontend
npm install
cd ..
```

2) Environment variables (create a `.env` in project root or set in shell)

```
PORT=5000
MONGO_URI=mongodb://127.0.0.1:27017/ecomm
JWT_SECRET=your_jwt_secret
EMAIL_HOST=...
EMAIL_PORT=...
EMAIL_USER=...
EMAIL_PASS=...
RAZORPAY_KEY_ID=...
RAZORPAY_KEY_SECRET=...
```

3) Start backend

```
npm run server
# Server: http://localhost:5000
```

4) Start React frontend

```
npm run client
# React: http://localhost:3000
```



---

## 📡 API Endpoints (selected)

- Products: `GET /api/v1/products`
- Users: `POST /api/v1/users/login`, `GET /api/v1/users/profile`
- Orders: `POST /api/v1/orders`, `GET /api/v1/orders/:id`
- Payment (Razorpay): under `/api/v1/payment/razorpay/*`

---

## 🧪 Development Scripts

Root scripts:

```
npm run server        # start backend with nodemon
npm run client        # start React app
npm run dev           # start backend + React concurrently
```

---

## 🍀 Database Seeding

Seed development data into MongoDB using the built-in scripts:

```
# Import sample users and products
npm run data:import

# Destroy all data (use with caution)
npm run data:destroy
```

Seed sources:
- Users: `backend/data/users.js` (default admin: `admin@admin.com` / `admin123`)
- Products: `backend/data/products.js`

Ensure your MongoDB is running and `MONGO_URI` is set in `.env` before seeding.

---

## 📦 Production Build & Deployment

Build the React app and serve it from the backend in production mode:

```
# In the React app
cd frontend
npm run build

# Back to project root and start with NODE_ENV=production
cd ..
set NODE_ENV=production&& npm start   # PowerShell: $env:NODE_ENV='production'; npm start
```

Notes:
- The backend `server.js` serves `frontend/build` when `NODE_ENV=production`.
- Ensure environment variables are set on your server (PORT, MONGO_URI, JWT_SECRET, etc.).

---

## 📁 Folder Details

- `backend/config`          – DB and email config
- `backend/controllers`     – Route handlers (products, users, orders, payments)
- `backend/middleware`      – Auth, error handling, validators
- `backend/models`          – Mongoose schemas
- `backend/routes`          – Express routers under `/api/v1/*`
- `backend/utils`           – Helpers (file handling, token generation)
- `backend/seeder.js`       – Seed and destroy database data
- `frontend/src`            – React source code
- `uploads/`                – Static image uploads served at `/uploads`

---

