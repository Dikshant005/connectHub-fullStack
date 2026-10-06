# 🎥 ConnectHub

ConnectHub is a full-stack, real-time video conferencing and collaboration platform featuring peer-to-peer and SFU video calls, instant messaging, file sharing, and AI-assisted meeting summaries.

---

## 🔗 Project Links

* **Live Link:** `https://connect-hub-frontend-beryl.vercel.app/`
* **Original Component Repositories:**
  * Backend: [github.com/Dikshant005/connectHub](https://github.com/Dikshant005/connectHub)
  * Frontend: [github.com/Dikshant005/ConnectHub-frontend](https://github.com/Dikshant005/ConnectHub-frontend)

---

## 🏗️ Project Structure

```text
ConnectHub/
├── backend/                  # Node.js / Express REST API, Socket.IO & LiveKit signaling
│   ├── models/               # MongoDB Mongoose schemas
│   ├── routes/               # API routes (auth, meetings, chat)
│   ├── middleware/           # JWT authentication middleware
│   ├── utils/                # S3 uploads, email, and helper functions
│   └── .env.example          # Template for backend environment variables
├── frontend/                 # React (Vite) client application
│   ├── src/
│   │   ├── Components/       # UI Views (Meeting, Chat, Auth, Dashboard)
│   │   ├── Providers/        # Context & Socket providers
│   │   └── Hooks/            # Custom React hooks
│   └── package.json
├── package.json              # Root package with monorepo convenience scripts
├── .gitignore                # Global gitignore preventing secret or dependency leaks
└── README.md
```

---

## 🛠️ Tech Stack

* **Frontend:** React 19, Vite, Socket.IO Client, LiveKit Client, React Router DOM, React Toastify
* **Backend:** Node.js, Express, Socket.IO, LiveKit Server SDK, MongoDB (Mongoose), AWS S3 SDK, Google Gemini AI, Nodemailer
* **Real-time Media:** LiveKit Cloud & WebRTC
* **Storage & Cloud:** AWS S3 (files/recordings), MongoDB Atlas

---

## ✨ Key Features

1. **High-Definition Video & Audio:** Multi-party video conferences powered by LiveKit SFU/WebRTC.
2. **Real-Time Chat & Signaling:** Low-latency in-meeting messaging via Socket.IO.
3. **AI Meeting Summaries:** Meeting reports and automated summaries powered by Google Gemini API.
4. **Cloud Storage:** Secure file uploads and recording assets persisted directly to AWS S3.
5. **Authentication & Password Recovery:** JWT-based secure sessions with SMTP email verification.

---

## 🚀 Getting Started

### Prerequisites

* [Node.js](https://nodejs.org/) (v18.x or higher)
* [npm](https://www.npmjs.com/) (v9.x or higher)
* MongoDB instance (local or Atlas)

---

### Method 1: Manual Step-by-Step (Recommended)

#### 1. Clone the repository
```bash
git clone https://github.com/Dikshant005/connectHub-fullStack.git
cd ConnectHub-full
```

#### 2. Start Backend Server
```bash
cd backend
npm install
cp .env.example .env
# Edit .env with your MongoDB URI, JWT secret, and API keys
npm run dev
```
*Backend will run on `http://localhost:3000` (or the configured `PORT`).*

#### 3. Start Frontend Client
Open a second terminal window:
```bash
cd frontend
npm install
npm run dev
```
*Frontend will launch on Vite's default dev server (typically `http://localhost:5173`).*

---

### Method 2: Monorepo Root Scripts

From the root directory (`ConnectHub-full`):

```bash
# Install dependencies for both backend and frontend
npm run install:all

# In Terminal 1: Run Backend
npm run backend

# In Terminal 2: Run Frontend
npm run frontend
```

---

## 🔐 Environment Variables

The backend requires the environment variables outlined in [`backend/.env.example`](./backend/.env.example):

| Variable | Description |
| :--- | :--- |
| `MONGO_URI` | MongoDB connection string |
| `PORT` | Server listening port (default: `3000`) |
| `JWT_SECRET` | Secret token used to sign JSON Web Tokens |
| `GEMINI_API_KEY` | Google Gemini AI key for meeting reports |
| `AWS_REGION` | AWS Region for S3 |
| `AWS_ACCESS_KEY_ID` | AWS IAM Access Key ID |
| `AWS_SECRET_ACCESS_KEY` | AWS IAM Secret Access Key |
| `AWS_S3_BUCKET` | AWS S3 Bucket Name |
| `LIVEKIT_URL` | LiveKit Cloud WebSocket URL |
| `LIVEKIT_API_KEY` | LiveKit API Key |
| `LIVEKIT_API_SECRET` | LiveKit API Secret |
| `SMTP_USER` / `SMTP_PASS` | Nodemailer credentials for email delivery |
