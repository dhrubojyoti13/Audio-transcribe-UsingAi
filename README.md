<h1 align="center">🎙️ AI Audio-to-Text Transcriber</h1>

<p align="center">
  A full-stack web application that converts uploaded audio into text using the <b>Google Gemini API</b>,
  built with <b>Spring Boot</b> (REST backend) and <b>React</b> (frontend).
</p>

<p align="center">
  <img alt="Java" src="https://img.shields.io/badge/Java-17-orange?logo=openjdk&logoColor=white">
  <img alt="Spring Boot" src="https://img.shields.io/badge/Spring%20Boot-REST%20API-6DB33F?logo=springboot&logoColor=white">
  <img alt="React" src="https://img.shields.io/badge/React-Frontend-61DAFB?logo=react&logoColor=black">
  <img alt="Gemini API" src="https://img.shields.io/badge/Google-Gemini%20API-4285F4?logo=google&logoColor=white">
  <img alt="Maven" src="https://img.shields.io/badge/Build-Maven-C71A36?logo=apachemaven&logoColor=white">
</p>

<!-- Add a live demo link here if you deploy the app:
<p align="center"><a href="YOUR_LIVE_LINK">🔗 Live Demo</a></p>
-->

---

## 📖 Overview

**AI Audio-to-Text Transcriber** lets a user upload an audio file and receive an accurate text transcript. The React frontend sends the file to a Spring Boot REST API, which validates the upload, calls the Google Gemini API for speech recognition, and returns the transcript to the user.

The project demonstrates **generative AI integration in a Java backend**, clean **REST API design**, input validation, error handling, and secure API key management.

## ✨ Features

- 🎧 **Audio upload** through a simple React interface
- 🤖 **AI speech-to-text** powered by the Google Gemini API
- ✅ **Server-side validation** of file type and size (under 1 MB)
- 🛡️ **Exception handling** for invalid input and API failures
- 🧱 **Layered backend architecture** (Controller, Service, Config)
- 🔐 **Secure API key management** using environment variables
- ⏳ **Clear UI states** for uploading, loading, success, and errors

## 🖼️ Screenshots

<!-- Replace these with real screenshots. Create a /screenshots folder in the repo. -->

| Upload screen | Transcript result |
|---|---|
| ![Upload](screenshots/upload.png) | ![Result](screenshots/result.png) |

## 🏗️ How It Works

```
User ──► React UI ──► Spring Boot REST API ──► Google Gemini API
 ▲            │              │                        │
 │            │       validates file type             │
 │            │       and size (under 1 MB)           │
 └────────────┴──────── transcript (text) ◄───────────┘
```

1. The user uploads an audio file in the React app.
2. React sends the file to the Spring Boot backend using Axios (multipart request).
3. The backend validates the file, then sends it to the Gemini API.
4. The transcript is returned and displayed in the UI.

## 🛠️ Tech Stack

| Layer | Technologies |
|---|---|
| **Backend** | Java, Spring Boot, REST APIs, Maven |
| **Frontend** | React, Axios, HTML, CSS, JavaScript |
| **AI** | Google Gemini API |
| **Tools** | Git, GitHub, Postman |

## 📁 Project Structure

<!-- Update this tree to match your actual folders. -->

```
Audio-transcribe-UsingAi/
├── backend/         # Spring Boot application (Controller, Service, Config)
├── frontend/        # React application
└── README.md
```

## 🚀 Getting Started

### Prerequisites

- Java 17 or later
- Maven
- Node.js and npm
- A Google Gemini API key ([get one from Google AI Studio](https://aistudio.google.com/))

### 1. Clone the repository

```bash
git clone https://github.com/dhrubojyoti13/Audio-transcribe-UsingAi.git
cd Audio-transcribe-UsingAi
```

### 2. Run the backend

```bash
cd backend
# Set your API key as an environment variable (use the name your code reads)
export GEMINI_API_KEY=your_api_key_here      # macOS / Linux
# set GEMINI_API_KEY=your_api_key_here       # Windows (cmd)

mvn spring-boot:run
```

The API starts on `http://localhost:8080` by default.

### 3. Run the frontend

```bash
cd frontend
npm install
npm start
```

Open the URL shown in the terminal (usually `http://localhost:3000`).

> ⚠️ **Never commit your API key.** Keep it in environment variables or an untracked local config file.

## 🔌 API Endpoint

<!-- Update the path and field names to match your controller. -->

| Method | Endpoint | Description |
|---|---|---|
| `POST` | `/api/transcribe` | Upload an audio file (multipart form data) and receive the transcript |

**Example request (cURL):**

```bash
curl -X POST http://localhost:8080/api/transcribe \
  -F "file=@sample-audio.mp3"
```

## ⚠️ Limitations

- Maximum upload size is under **1 MB** per file.
- Transcription quality depends on audio clarity and the Gemini API.

## 🔮 Future Improvements

- Support for larger files with asynchronous processing
- Transcript history stored in a database
- Download transcript as TXT or PDF
- Support for more audio formats and languages
- Unit and integration tests with JUnit
- Docker setup and cloud deployment

## 👨‍💻 Author

**Dhrubojyoti Sarkar**
Java Full-Stack Developer | Spring Boot, React, REST APIs

[![GitHub](https://img.shields.io/badge/GitHub-dhrubojyoti13-181717?logo=github)](https://github.com/dhrubojyoti13)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-dhrus13-0A66C2?logo=linkedin&logoColor=white)](https://linkedin.com/in/dhrus13)

---

⭐ If you find this project useful, please consider giving it a star!

**Keywords:** audio to text, speech to text, transcription, Google Gemini API, Spring Boot, React, REST API, full-stack, generative AI, Java
