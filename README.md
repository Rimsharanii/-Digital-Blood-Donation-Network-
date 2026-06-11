🩸 Digital Blood Donation Network
A web-based platform developed to connect blood donors with patients in need, streamlining the process of blood donation requests, donor registration, and real-time communication — built as a Final Year Project.

📋 Project Overview
The Digital Blood Donation Network is a full-stack MERN application that addresses the critical challenge of finding compatible blood donors quickly during medical emergencies. The system provides a centralized platform where donors can register their availability, patients or hospitals can post blood requests, and both parties can connect efficiently through a secure, verified process.
Problem Statement
In emergency situations, finding the right blood group from a compatible donor is time-consuming and often relies on manual phone calls and social media posts. This platform digitalizes and automates that process.
Objectives

To provide a centralized database of registered blood donors
To enable patients to post urgent blood requests
To implement secure user authentication with OTP email verification
To create a responsive, accessible interface usable on any device
To automate deployment using modern CI/CD practices


✨ Key Features

User Authentication — Secure registration and login using JWT tokens and bcrypt password hashing
OTP Verification — Email-based one-time password verification via Nodemailer
Donor Registration — Donors can register with blood group, city, contact info, and availability status
Blood Request Management — Patients can post, update, and manage blood requests
Donor Search — Filter donors by blood group and location
Feedback System — Users can submit ratings and reviews
Responsive Design — Fully mobile-friendly UI built with Tailwind CSS
Auto Deployment — Continuous deployment pipeline via GitHub and Vercel


🛠️ Technology Stack
LayerTechnologyFrontendReact.js, React Router v6, Tailwind CSS, AxiosBackendNode.js (v18/24), Express.jsDatabaseMongoDB Atlas (Cloud)AuthenticationJSON Web Tokens (JWT), bcryptEmail ServiceNodemailerHostingVercel (Frontend + CDN)Version ControlGit, GitHubCI/CDVercel Auto-Deploy

🏗️ System Architecture
Browser (Chrome / Firefox / Safari / Edge)
             │  HTTPS · TLS 1.3
             ▼
┌────────────────────────────────────┐
│         Vercel CDN                 │
│   React.js Single Page Application │
│   React Router · Tailwind · Axios  │
└────────────────────────────────────┘
             │  HTTPS REST · JSON
             ▼
┌────────────────────────────────────┐
│      Express.js API Server         │
│         Node.js 18/24              │
│                                    │
│  Middleware: JWT · bcrypt ·        │
│             Nodemailer             │
│                                    │
│  Services: User · Donor ·          │
│   Blood Request · Feedback · OTP   │
└────────────────────────────────────┘
             │  MongoDB Wire Protocol · TLS
             ▼
┌────────────────────────────────────┐
│          MongoDB Atlas             │
│  Collections: users · donors ·     │
│  blood_requests · feedback · otps  │
└────────────────────────────────────┘

CI/CD: GitHub Push → Vercel Build → Auto Deploy

📁 Project Structure
digital-blood-donation-network/
│
├── client/                    # Frontend (React.js)
│   └── src/
│       ├── components/        # Reusable UI components
│       ├── pages/             # Application pages
│       ├── services/          # Axios API call functions
│       └── App.jsx            # Root component & routing
│
├── server/                    # Backend (Express.js)
│   ├── config/                # Database connection
│   ├── controllers/           # Route handler logic
│   ├── middleware/            # JWT auth & error handling
│   ├── models/                # Mongoose data schemas
│   ├── routes/                # API route definitions
│   ├── services/              # Business logic modules
│   └── server.js              # Entry point
│
└── README.md



⚙️ Installation & Setup
Requirements

Node.js v18 or above
MongoDB Atlas account
Gmail account (for email/OTP service)

Steps
bash# 1. Clone the repository
git clone https://github.com/your-username/digital-blood-donation-network.git

# 2. Install backend dependencies
cd server && npm install

# 3. Install frontend dependencies
cd ../client && npm install

# 4. Create .env file in /server with the following:
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key
EMAIL_USER=your_email@gmail.com
EMAIL_PASS=your_email_app_password
CLIENT_URL=http://localhost:3000

# 5. Run the application
cd server && npm run dev     # Backend on port 5000
cd client && npm start       # Frontend on port 3000

🚀 Deployment
The application is deployed using Vercel with an automated CI/CD pipeline:

Code is pushed to the main branch on GitHub
Vercel detects the push via webhook
The build and test process runs automatically
On success, the updated application is deployed live to the global CDN

Live URL: https://your-app.vercel.app

🔒 Security Measures

Passwords are hashed using bcrypt before storage — never stored as plain text
All protected routes require a valid JWT token in the request header
Email verification via OTP prevents fake account registration
Database connection uses TLS encryption via MongoDB Atlas
Environment variables store all sensitive credentials — never hardcoded


📄 License
This project is submitted as an academic Final Year Project at [Your Institution Name].
All rights reserved © 2025 — [Your Full Name]


"Every drop counts — technology can help deliver it faster."
