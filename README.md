![React](https://img.shields.io/badge/Frontend-React%2017-blue?logo=react)
![Node.js](https://img.shields.io/badge/Backend-Node.js-green?logo=node.js)
![MongoDB](https://img.shields.io/badge/Database-MongoDB-green?logo=mongodb)
![React Native](https://img.shields.io/badge/Mobile-React%20Native%20%2F%20Expo-blueviolet?logo=expo)
![Flask](https://img.shields.io/badge/ML-Flask-lightgrey?logo=flask)
![License](https://img.shields.io/badge/License-MIT-green)

# Study Buddy

A full-stack student productivity and academic management platform. Study Buddy combines a **React web dashboard**, a **React Native mobile app** (Expo), a **Node.js REST API**, and two **Flask ML microservices** to give students personalized study recommendations, attendance tracking, document management, and academic performance insights.

## Features

- **Authentication** — JWT-based registration and login with bcrypt password hashing
- **Student Dashboard** — attendance overview, calendar, performance charts (ApexCharts)
- **Document Management** — upload and browse study documents (Multer)
- **Study Recommendations** — ML-powered suggestions based on student performance
- **Emotion/NLP Feedback** — sentiment analysis on student feedback text
- **Email Notifications** — nodemailer + SendGrid for transactional emails
- **Mobile App** — React Native (Expo) with screens for Login, Home, Recommendations, Documents, Attendance, Profile, and Entry Records
- **ML Microservices** — two Flask APIs: student performance predictor and text emotion/spam classifier

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Web Frontend | React 17, Chakra UI, Framer Motion, ApexCharts, Axios |
| Mobile | React Native, Expo, react-navigation |
| Backend API | Node.js, Express, Mongoose, JWT, bcryptjs, Multer, Nodemailer |
| Database | MongoDB |
| ML Services | Flask, Scikit-learn, Pandas (2 microservices) |
| Testing | Jest, Supertest, mongodb-memory-server |

## Architecture

```
Study-Buddy/
├── frontend/       React web dashboard (Chakra UI)
├── backend/        Node.js / Express REST API (MongoDB)
├── mobile app/     React Native (Expo) mobile client
└── ml/
    ├── Student-Flask/      Student performance prediction API
    └── Text-Emotion-NLP/   Feedback sentiment / spam classifier API
```

## Getting Started

### Backend (Node.js API)

```bash
cd backend
npm install
# Create a .env file with MONGO_URI, JWT_SECRET, SENDGRID_API_KEY
npm run dev         # starts with nodemon on port 5000
```

### Frontend (React)

```bash
cd frontend
npm install
npm start           # opens at http://localhost:3000
```

### Mobile App (Expo)

```bash
cd "mobile app"
npm install
npx expo start      # scan QR code with Expo Go app
```

### ML Services (Flask)

```bash
# Student performance predictor
cd ml/Student-Flask
pip install flask scikit-learn pandas numpy
python app.py       # runs on http://localhost:5000

# Text emotion / NLP
cd ml/Text-Emotion-NLP
python app.py       # runs on http://localhost:5001
```

## API Endpoints (Backend)

| Method | Endpoint | Description |
|--------|----------|-------------|
| POST | `/api/auth/register` | Register a new student |
| POST | `/api/auth/login` | Login and receive JWT |
| GET | `/api/students/` | Get student profile |
| POST | `/api/documents/upload` | Upload study document |
| GET | `/api/attendance/` | Fetch attendance records |

## ML API Endpoints

| Service | Endpoint | Input | Output |
|---------|----------|-------|--------|
| Student-Flask | `POST /predict` | Student metrics | Performance prediction |
| Text-Emotion-NLP | `POST /predict` | Feedback text | Emotion / spam label |

## License

MIT License — see [LICENSE](LICENSE) for details.
