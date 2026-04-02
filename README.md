# ⚙️ DocSync Backend (API + Real-Time Server)

This is the backend service for **DocSync**, a real-time clinic queue management system.
It handles authentication, appointments, queue management, payments, notifications, and real-time updates using WebSockets.

---

## 🚀 Features

* 🔐 JWT Authentication (Patient, Doctor, Admin)
* 📅 Appointment Booking & Management
* 🔄 Real-Time Queue System (Socket.IO)
* ⏱️ Wait-Time Prediction Engine
* 💳 Payment Ledger Management
* 🔔 Push Notifications (optional)
* 🧾 Logging & Error Handling

---

## 🏗️ Project Structure

```
backend/
│
├── src/
│   ├── config/
│   │   ├── db.js              # MongoDB connection
│   │   ├── serverConfig.js    # Server configuration
│   │   └── socket.js          # Socket.IO setup
│   │
│   ├── models/                # Mongoose models
│   │   ├── User.js
│   │   ├── Doctor.js
│   │   ├── Appointment.js
│   │   ├── Queue.js
│   │   ├── Payment.js
│   │   └── Notification.js
│   │
│   ├── controllers/           # Business logic
│   │   ├── authController.js
│   │   ├── userController.js
│   │   ├── doctorController.js
│   │   ├── appointmentController.js
│   │   ├── queueController.js
│   │   ├── paymentController.js
│   │   └── notificationController.js
│   │
│   ├── routes/                # API endpoints
│   │   ├── authRoutes.js
│   │   ├── userRoutes.js
│   │   ├── doctorRoutes.js
│   │   ├── appointmentRoutes.js
│   │   ├── queueRoutes.js
│   │   ├── paymentRoutes.js
│   │   └── notificationRoutes.js
│   │
│   ├── middleware/            # Middleware functions
│   │   ├── authMiddleware.js
│   │   ├── roleMiddleware.js
│   │   ├── errorMiddleware.js
│   │   └── validateMiddleware.js
│   │
│   ├── services/              # Core logic services
│   │   ├── queueService.js
│   │   ├── predictionService.js
│   │   ├── tokenService.js
│   │   └── pushNotificationService.js
│   │
│   ├── sockets/               # Real-time logic
│   │   └── queueSocket.js
│   │
│   ├── utils/                 # Helper utilities
│   │   ├── generateToken.js
│   │   ├── jwt.js
│   │   ├── logger.js
│   │   └── responseHandler.js
│   │
│   ├── app.js                 # Express app setup
│   └── server.js              # Entry point
│
├── .env                       # Environment variables
├── package.json              # Dependencies
```

---

## 🛠️ Tech Stack

* Node.js
* Express.js
* MongoDB (Mongoose)
* Socket.IO
* JSON Web Token (JWT)
* Bcrypt (Password hashing)

---

## ⚡ Getting Started

### 1. Install Dependencies

```
npm install
```

---

### 2. Setup Environment Variables

Create a `.env` file in root:

```
PORT=5000
MONGO_URI=your_mongodb_connection
JWT_SECRET=your_secret_key
```

---

### 3. Run Server

```
npm run dev
```

---

## 📡 API Overview

### Auth

* POST `/api/auth/register`
* POST `/api/auth/login`

### Appointments

* POST `/api/appointments`
* GET `/api/appointments`

### Queue

* GET `/api/queue`
* PUT `/api/queue/next`
* PUT `/api/queue/skip`
* PUT `/api/queue/done`

### Payments

* GET `/api/payments`
* POST `/api/payments`

---

## 🔄 Real-Time System

* Socket.IO is used for live queue updates
* When admin updates queue:

  * All connected clients receive updates instantly
* Events handled in:

  * `src/sockets/queueSocket.js`

---

## 🧠 Key Concepts

* RESTful API design
* Role-based access control
* Real-time communication (WebSockets)
* Modular backend architecture
* Separation of concerns (MVC + Services)

---

## ⚠️ Notes

* Ensure MongoDB is running (local or Atlas)
* Use Postman for API testing
* Socket must be connected on frontend for real-time updates

---

## 👨‍💻 Author

Muhammad Farooq
