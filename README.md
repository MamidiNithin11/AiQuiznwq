Perfect 🔥 — here’s a **complete, professional `README.md`** for your **AI Wiki Quiz Generator** project.

It’s written in clean Markdown — ready to upload to **GitHub** — and includes setup, environment variables, usage, project structure, API routes, and contribution details.

---

## 🧠 **README.md**

```markdown
# 🧠 AI Wiki Quiz Generator

An intelligent web application that scrapes Wikipedia articles, uses Google's Gemini AI to generate multiple-choice quizzes, and stores them in a PostgreSQL database.  
The frontend (built with **Vite + React**) lets users input any Wikipedia URL, view AI-generated quizzes, and revisit their quiz history.

---

## 🚀 Features

✅ Scrape Wikipedia pages automatically  
✅ Generate quizzes using **Gemini AI (LangChain integration)**  
✅ Store quizzes in **PostgreSQL**  
✅ RESTful backend powered by **FastAPI**  
✅ Frontend built with **Vite + React + TailwindCSS**  
✅ Quiz history tracking and detailed quiz view  
✅ Full CORS support for smooth frontend-backend communication  

---

## 🧩 Tech Stack

| Layer | Technologies Used |
|-------|-------------------|
| **Frontend** | Vite, React, TailwindCSS, Axios |
| **Backend** | FastAPI, LangChain, SQLAlchemy |
| **AI Model** | Gemini 1.5 / 2.5 (via Google Generative AI) |
| **Database** | PostgreSQL |
| **Environment** | Python 3.10+ |

---

## 📁 Project Structure


aai-quiz-generators/
├── backend/
│   ├── __init__.py
│   ├── database.py
│   ├── llm_quiz_generator.py
│   ├── main.py
│   ├── models.py
│   ├── requirements.txt
│   ├── scraper.py
│   └── __pycache__/
└── frontend/
    ├── App.jsx
    ├── index.html
    ├── index.jsx
    ├── metadata.json
    ├── package.json
    ├── README.md
    ├── types.ts
    ├── vite.config.ts
    ├── assets/
    ├── components/
    │   ├── GenerateQuizTab.jsx
    │   ├── HistoryTab.jsx
    │   ├── Modal.jsx
    │   ├── QuizDisplay.jsx
    │   └── icons/
    │       ├── BookOpenIcon.jsx
    │       ├── CheckIcon.jsx
    │       ├── ClipboardIcon.jsx
    │       ├── ClockIcon.jsx
    │       ├── CogIcon.jsx
    │       ├── ExternalLinkIcon.jsx
    │       ├── HistoryIcon.jsx
    │       ├── InfoIcon.jsx
    │       ├── LoaderIcon.jsx
    │       ├── TrophyIcon.jsx
    │       └── XIcon.jsx
    └── services/
        └── api.js

    

## ⚙️ Backend Setup (FastAPI)

### 1️⃣ Clone the repository

```bash
git clone https://github.com/<your-username>/ai-quiz-generator.git
cd ai-quiz-generator/backend
````

### 2️⃣ Create a virtual environment

```bash
python -m venv venv
.\venv\Scripts\activate      # Windows
```

### 3️⃣ Install dependencies

```bash
pip install -r requirements.txt
```

### 4️⃣ Configure environment variables

Create a `.env` file inside `/backend`:

```env
DATABASE_URL=postgresql+psycopg2://username:password@localhost:5432/quizdb
GEMINI_API_KEY=your_gemini_api_key_here
```

> 🧠 Note: Replace `username`, `password`, and `quizdb` with your actual PostgreSQL credentials.

### 5️⃣ Initialize the database

Make sure PostgreSQL is running, then FastAPI will auto-create tables when starting.

### 6️⃣ Run the backend server

```bash
uvicorn main:app --reload
```

Your backend will start at 👉 **[http://127.0.0.1:8000](http://127.0.0.1:8000)**

---

## 🌐 API Endpoints

| Method | Endpoint         | Description                        |
| ------ | ---------------- | ---------------------------------- |
| `GET`  | `/`              | Health check                       |
| `POST` | `/generate_quiz` | Generate quiz from a Wikipedia URL |
| `GET`  | `/history`       | List all saved quizzes             |
| `GET`  | `/quiz/{id}`     | Get full quiz details by ID        |

### 🧾 Example Response (`/generate_quiz`)

```json
{
  "id": 1,
  "url": "https://en.wikipedia.org/wiki/Alan_Turing",
  "title": "Alan Turing",
  "summary": "Alan Turing was a British mathematician...",
  "key_entities": {
    "people": ["Alan Turing", "Alonzo Church"],
    "organizations": ["University of Cambridge", "Bletchley Park"],
    "locations": ["United Kingdom"]
  },
  "sections": ["Early life", "World War II", "Legacy"],
  "quiz": [
    {
      "question": "Where did Alan Turing study?",
      "options": ["Harvard", "Cambridge", "Oxford", "Princeton"],
      "answer": "Cambridge",
      "difficulty": "easy",
      "explanation": "Mentioned in the 'Early life' section."
    }
  ],
  "related_topics": ["Cryptography", "Enigma machine", "Computer science history"]
}
```

---

## 💻 Frontend Setup (Vite + React)

### 1️⃣ Navigate to frontend

```bash
cd ../frontend
```

### 2️⃣ Install dependencies

```bash
npm install
```

### 3️⃣ Start the Vite development server

```bash
npm run dev
```

Your frontend will run on 👉 **[http://localhost:5173](http://localhost:5173)**

### 4️⃣ Configure backend URL (if needed)

In `src/services/api.js`, ensure this matches your backend:

```javascript
export const API_BASE_URL = "http://127.0.0.1:8000";
```

---

## 🔗 Frontend API Calls

* **Generate Quiz:**
  Sends POST → `/generate_quiz?url=<Wikipedia_URL>`

* **Fetch History:**
  GET → `/history`

* **Fetch Quiz by ID:**
  GET → `/quiz/<id>`

---

## 🧰 Environment Requirements

| Tool       | Version |
| ---------- | ------- |
| Python     | 3.10+   |
| Node.js    | 18+     |
| PostgreSQL | 14+     |
| Vite       | 5.x     |
| FastAPI    | 0.110+  |

---

## 🧑‍💻 Development Notes

* The backend automatically creates tables using SQLAlchemy.
* Use the `/docs` endpoint to test all APIs via Swagger UI.
* If quiz generation fails, check your Gemini API key and ensure `.env` is configured correctly.

---

## 📦 Example `.env` File

```env
# Backend environment
DATABASE_URL=postgresql+psycopg2://postgres:password@localhost:5432/quizdb
GEMINI_API_KEY=AIzaSyExampleKey
```

---

## 🤝 Contributing

1. Fork this repo
2. Create a feature branch (`feature/new-ui`)
3. Commit changes (`git commit -m "Add new quiz result UI"`)
4. Push to your branch and open a Pull Request 🎯

---

## 🧠 Future Enhancements

* User authentication (login-based quiz tracking)
* Leaderboard system
* Custom quiz generation from uploaded documents
* Dark mode UI
* Export quizzes to PDF

---

## 🛡️ License

This project is licensed under the **MIT License**.
Feel free to use, modify, and distribute for personal or commercial use.

---

## 💬 Credits

Developed by **[Your Name]**
🧠 Powered by **Gemini AI + FastAPI + Vite React**


outpus:

<img width="1915" height="971" alt="Screenshot 2025-10-26 021429" src="https://github.com/user-attachments/assets/c467f4ea-b4f8-4817-b8b7-452de7ee3e6d" />

_______________________________________________________________________________________________________________________________________________________________

<img width="1902" height="963" alt="Screenshot 2025-10-26 021521" src="https://github.com/user-attachments/assets/e940f35e-d080-4aea-8f09-a5ab86ba5c79" />

_______________________________________________________________________________________________________________________________________________________________



<img width="1328" height="966" alt="Screenshot 2025-10-26 012001" src="https://github.com/user-attachments/assets/8a60b449-77a5-4147-bebc-aee645107a67" />

_______________________________________________________________________________________________________________________________________________________________



<img width="1261" height="952" alt="Screenshot 2025-10-26 012140" src="https://github.com/user-attachments/assets/155c0b08-e1ea-4933-9b01-8427a360c1af" />

_______________________________________________________________________________________________________________________________________________________________



<img width="1318" height="962" alt="Screenshot 2025-10-26 012156" src="https://github.com/user-attachments/assets/41c6bc63-b4cf-454d-b220-11d7e24220a7" />

_______________________________________________________________________________________________________________________________________________________________




<img width="1414" height="951" alt="Screenshot 2025-10-26 012212" src="https://github.com/user-attachments/assets/66a4243e-4c86-47ce-be93-43856b48bc19" />
_______________________________________________________________________________________________________________________________________________________________



<img width="1428" height="947" alt="Screenshot 2025-10-26 012232" src="https://github.com/user-attachments/assets/a51c0ce0-05d9-4427-9644-4f382571e3c3" />
_______________________________________________________________________________________________________________________________________________________________



<img width="910" height="954" alt="Screenshot 2025-10-26 012111" src="https://github.com/user-attachments/assets/b0fd47d1-4c8d-42ba-9534-d6c6c8395ca7" />
_______________________________________________________________________________________________________________________________________________________________




<img width="961" height="964" alt="Screenshot 2025-10-26 012100" src="https://github.com/user-attachments/assets/360f78cc-41ae-4daf-b95c-c2d1d95522ad" />





### ✅ Tips Before Pushing to GitHub

1. Place this file in your project root as `README.md`.  
2. Run:
   ```bash
   git add .
   git commit -m "Add detailed README file"
   git push origin main


3. On GitHub, it will automatically render beautifully on your repo’s main page.
