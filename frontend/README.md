🧠 AI Wiki Quiz Generator — Frontend

### 📋 Overview

The **AI Wiki Quiz Generator** frontend is a React + Vite-based web app that allows users to enter a Wikipedia URL and generate interactive quizzes using AI (Gemini API via FastAPI backend).

This project connects seamlessly with the backend service to:

* Scrape Wikipedia content
* Generate quizzes using the Gemini LLM
* Display interactive multiple-choice questions

---

## 🚀 Features

* 🔗 Input any **Wikipedia URL**
* ⚙️ Fetches AI-generated quizzes from FastAPI backend
* 💾 Displays quiz questions dynamically
* 🎯 Select difficulty-based questions (Easy / Medium / Hard)
* 🎨 Modern UI built with **Vite + React**
* 🌍 CORS-enabled communication with backend API

---

## 🏗️ Tech Stack

| Category           | Technology                           |
| ------------------ | ------------------------------------ |
| Frontend Framework | React (Vite)                         |
| Language           | JavaScript                           |
| HTTP Client        | Axios / Fetch API                    |
| Styling            | Tailwind CSS                         |
| Deployment         | Vercel                               |
| Backend Connection | FastAPI (Hosted on Render / Railway) |

---

## ⚙️ Project Structure

```
frontend/
├── public/
├── src/
│   ├── components/
│   │   ├── QuizCard.jsx
│   │   ├── QuizList.jsx
│   │   └── Loader.jsx
│   ├── pages/
│   │   ├── Home.jsx
│   │   ├── History.jsx
│   │   └── QuizDetails.jsx
│   ├── App.jsx
│   ├── main.jsx
│   └── api.js
├── index.html
├── package.json
├── vite.config.js
└── README.md
```

---

## 🧩 Environment Setup

### 1️⃣ Install Node.js

Make sure you have **Node.js (v18 or higher)** installed.

```bash
node -v
npm -v
```

---

### 2️⃣ Clone the Repository

```bash
git clone https://github.com/yourusername/ai-quiz-frontend.git
cd ai-quiz-frontend
```

---

### 3️⃣ Install Dependencies

```bash
npm install
```

---

This variable tells your frontend which backend API to call.

---

### 5️⃣ Run Locally

```bash
npm run dev
```

The app will start at:
👉 **[http://localhost:5173](http://localhost:5173)**

---

## 🔌 API Integration

Your frontend will send requests to these backend endpoints:

| Endpoint         | Method | Description                          |
| ---------------- | ------ | ------------------------------------ |
| `/generate_quiz` | `POST` | Generate quiz from Wikipedia URL     |
| `/history`       | `GET`  | Get all previously generated quizzes |
| `/quiz/{id}`     | `GET`  | Get quiz details by ID               |

Example Axios call:

```js
const response = await fetch(`${import.meta.env.VITE_API_URL}/generate_quiz?url=${url}`, {
  method: 'POST'
});
```
### 1️⃣ Push to GitHub

Make sure your frontend code is pushed to a GitHub repo (e.g., `ai-quiz-frontend`).

### 2️⃣ Go to [Vercel](https://vercel.com/new)

* Import your repository.
* Configure:

  * **Framework:** React
  * **Root Directory:** `frontend`
  * **Build Command:** `npm install && npm run build`
  * **Output Directory:** `dist`


## 🧪 Testing

You can test by entering a Wikipedia URL such as:

```
https://en.wikipedia.org/wiki/Alan_Turing
```

Then click **“Generate Quiz”** to see dynamically created questions.

---

## 🛠️ Troubleshooting

| Issue                | Fix                                                      |
| -------------------- | -------------------------------------------------------- |
| `CORS error`         | Ensure backend has `CORSMiddleware(allow_origins=["*"])` |
| `.env not loading`   | Restart dev server after adding `.env`                   |
| `API not responding` | Verify backend URL and deployment on Render              |

---

## 📁 `.gitignore` (for frontend)

Add this file to ignore unnecessary files:

```
node_modules/
dist/
.env
.vscode/
.DS_Store
npm-debug.log*
yarn-debug.log*
yarn-error.log*
```
