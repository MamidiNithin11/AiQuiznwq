# 🧠 AI Wiki Quiz Generator

**An intelligent full-stack web app that turns any Wikipedia article into an interactive multiple-choice quiz using Gemini AI.**
Built with **FastAPI**, **LangChain**, **PostgreSQL**, and a modern **Vite + React + TailwindCSS** frontend.

---

## 🚀 Features

* 🔍 **Automatic Wikipedia Scraping** — Extracts structured content from any Wikipedia URL.
* 🤖 **AI Quiz Generation** — Uses **Google Gemini (via LangChain)** to generate high-quality MCQs.
* 💾 **Data Persistence** — Stores quizzes and history in **PostgreSQL**.
* ⚡ **Modern RESTful API** — Built using **FastAPI** with CORS enabled for frontend integration.
* 🧩 **Frontend (Vite + React)** — Responsive, elegant UI with quiz generation and history view.
* 📚 **Quiz History** — Access previously generated quizzes anytime.
* 🌍 **Full Stack Integration** — Seamless communication between backend and frontend.

---

## 🧠 Tech Stack

| Layer           | Technologies                     |
| --------------- | -------------------------------- |
| **Frontend**    | React (Vite), TailwindCSS, Axios |
| **Backend**     | FastAPI, LangChain, SQLAlchemy   |
| **AI Model**    | Google Gemini 1.5 / 2.5          |
| **Database**    | PostgreSQL                       |
| **Environment** | Python 3.10+                     |

---

## 📁 Project Structure

```bash
ai-quiz-generator/
├── backend/
│   ├── __init__.py
│   ├── database.py
│   ├── llm_quiz_generator.py
│   ├── main.py
│   ├── models.py
│   ├── scraper.py
│   ├── requirements.txt
│   └── .env
└── frontend/
    ├── App.jsx
    ├── index.jsx
    ├── vite.config.ts
    ├── components/
    │   ├── GenerateQuizTab.jsx
    │   ├── HistoryTab.jsx
    │   ├── QuizDisplay.jsx
    │   └── Modal.jsx
    └── services/
        └── api.js
```

---

## ⚙️ Backend Setup (FastAPI)

### 1️⃣ Clone Repository

```bash
git clone https://github.com/<your-username>/ai-quiz-generator.git
cd ai-quiz-generator/backend
```

### 2️⃣ Create Virtual Environment

```bash
python -m venv venv
.\venv\Scripts\activate   # (Windows)
```

### 3️⃣ Install Dependencies

```bash
pip install -r requirements.txt
```

### 4️⃣ Configure Environment Variables

Create a `.env` file in `/backend`:

```env
DATABASE_URL=postgresql+psycopg2://username:password@localhost:5432/quizdb
GEMINI_API_KEY=your_gemini_api_key_here
```

> ⚠️ Replace placeholders with your PostgreSQL credentials and valid Gemini API key.

### 5️⃣ Run Backend Server

```bash
uvicorn main:app --reload
```

Your API is live at 👉 **[http://127.0.0.1:8000](http://127.0.0.1:8000)**

---

## 🌐 API Endpoints

| Method | Endpoint         | Description                        |
| ------ | ---------------- | ---------------------------------- |
| `GET`  | `/`              | Health check                       |
| `POST` | `/generate_quiz` | Generate quiz from a Wikipedia URL |
| `GET`  | `/history`       | Fetch all saved quizzes            |
| `GET`  | `/quiz/{id}`     | Retrieve quiz details by ID        |

### 🧾 Example Response

```json
{
  "id": 1,
  "title": "Alan Turing",
  "url": "https://en.wikipedia.org/wiki/Alan_Turing",
  "summary": "Alan Turing was a British mathematician and computer scientist...",
  "quiz": [
    {
      "question": "Where did Alan Turing study?",
      "options": ["Harvard", "Cambridge", "Oxford", "Princeton"],
      "answer": "Cambridge",
      "difficulty": "easy",
      "explanation": "Mentioned in 'Early life' section."
    }
  ]
}
```

---

## 🖥️ Frontend Setup (Vite + React)

### 1️⃣ Create Project

```bash
npm create vite@latest frontend
# Select: React → JavaScript
cd frontend
```

### 2️⃣ Install Dependencies

```bash
npm install
npm install axios
```

### 3️⃣ Setup TailwindCSS

```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Update `tailwind.config.js`:

```js
content: ["./index.html", "./src/**/*.{js,jsx}"]
```

Import into `index.css`:

```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

---

## 🔗 API Integration (frontend/services/api.js)

```js
import axios from "axios";

const API_BASE = "http://127.0.0.1:8000";

export const generateQuiz = (url) =>
  axios.post(`${API_BASE}/generate_quiz?url=${encodeURIComponent(url)}`);

export const getHistory = () => axios.get(`${API_BASE}/history`);

export const getQuizById = (id) => axios.get(`${API_BASE}/quiz/${id}`);
```

---

## 🧰 Environment Requirements

| Tool       | Version |
| ---------- | ------- |
| Python     | 3.10+   |
| Node.js    | 18+     |
| PostgreSQL | 14+     |
| FastAPI    | 0.110+  |
| Vite       | 5.x     |

---

## 🧩 Key Features in Action

#### Quiz Home page:


<img width="1902" height="963" alt="Screenshot 2025-10-26 021521" src="https://github.com/user-attachments/assets/c98ac581-6164-4e72-9f0d-39989f2eba54" />


### 🔹 Generate Quiz

<img width="1893" height="967" alt="Screenshot 2025-10-26 011931" src="https://github.com/user-attachments/assets/54fd0593-5769-4827-855e-882fc7cedfdd" />
__________________________________________________________________________________

### Quiz Key Contents

<img width="910" height="954" alt="Screenshot 2025-10-26 012111" src="https://github.com/user-attachments/assets/ecac02a0-20e5-4a54-bd75-9b984816c992" />

#### Quiz Score Based Result :

<img width="1261" height="952" alt="Screenshot 2025-10-26 012140" src="https://github.com/user-attachments/assets/d97dc6a5-a56d-401d-8a85-2a85de76b081" />

### Correct answer with Green and Wrong answer Red after Submission of Quiz:
<img width="1318" height="962" alt="Screenshot 2025-10-26 012156" src="https://github.com/user-attachments/assets/13e702f3-65c8-4520-b611-2ab237a77855" />


### 🔹 View Quiz History

<img width="1414" height="951" alt="Screenshot 2025-10-26 012212" src="https://github.com/user-attachments/assets/c1c63178-1c0e-4c45-9cc5-f7d685ff9e32" />

---

## 🧑‍💻 Development Notes

* The backend automatically creates all tables using:

  ```python
  Base.metadata.create_all(bind=engine)
  ```
* Swagger UI available at → **`/docs`**
* If quiz generation fails:

  * Verify your Gemini API key
  * Check `.env` configuration
  * Ensure your database connection is active

---

## 🧠 Future Enhancements

* 🔐 User authentication & personalized quiz dashboards
* 🏆 Leaderboard and quiz scoring system
* 📂 Document-based custom quiz generation
* 🌙 Dark mode UI
* 📄 Export quizzes to PDF

---

## 🤝 Contributing

1. Fork the repository
2. Create your feature branch

   ```bash
   git checkout -b feature/new-ui
   ```
3. Commit your changes

   ```bash
   git commit -m "Add new quiz result UI"
   ```
4. Push and open a Pull Request 🎯

---

## 🛡️ License

Licensed under the **MIT License** — free to use and modify.

---

## 💬 Credits

Developed by MamidiNithin11
🧠 Powered by **Gemini AI**, **FastAPI**, and **React (Vite + TailwindCSS)**


