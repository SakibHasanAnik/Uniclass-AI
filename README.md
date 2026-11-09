# UniClass AI

**A University Learning Management System with an Explainable AI Student-Risk Advisor**

> CSE4104 Project · Team **CSE4104-7E-T04** · Section 7E
> Northern University of Business and Technology, Khulna · Department of CSE

---

## Team Information

| Field | Details |
|---|---|
| Team Name | CSE4104-7E-T04 |
| Section | 7E |
| Course | CSE4104 |
| Course Teacher | Md. Riaz Mahmud, Assistant Professor, Dept. of CSE |
| Team Leader | Sakib Hasan Anik (CSE230321575) |

| No. | Member Name | Student ID | Role |
|---|---|---|---|
| 1 | Sakib Hasan Anik | CSE230321575 | Team Leader · Database and AI |
| 2 | Arnab Basu | CSE230321361 | Backend Developer |
| 3 | Sarder Fariha Alam Trishna | CSE230321371 | Frontend Developer |

---

## Project Description

In most universities, information about a student's progress is spread across many places. Materials are shared in a classroom tool, marks are kept in teachers' spreadsheets, and attendance is taken on paper. An academic advisor responsible for many students rarely sees the full picture, so students who are struggling are usually noticed only after the semester results, when it is too late to help.

**UniClass AI** brings all of this into one web platform:

- **Teachers** manage course materials, assignments, marks and attendance.
- **Students** follow their own progress in every course.
- **Advisors** receive a weekly AI-generated list of students who may be at risk of failing. For each student the system explains *why* in plain language (for example, "attendance fell from 90% to 52%"), suggests an action, and drafts a supportive message the advisor can edit and send.
- **Admins** manage users, courses, enrollment and advisor assignments.

The AI does not replace the advisor. It shows them where to look first, and every decision stays with a human.

---

## Proposed Features

### Authentication
- Login page with **Student / Teacher / Advisor** role selection (`/login`)
- Separate admin login page (`/adminlogin`)
- Token-based login with a role check on every request

### Student Portal
- Dashboard with enrolled courses, attendance %, average marks and upcoming deadlines
- Course page: materials, assignment submission, results vs class average, attendance history
- Students never see risk scores

### Teacher Portal
- Dashboard: courses this term, total students, submissions to grade, today's classes, students needing attention
- Upload and manage course materials
- Create and grade assignments
- Create assessments (quiz, class test, midterm, final) and enter marks with validation
- Take attendance (present / late / absent)
- Class analytics with charts

### Advisor Portal (AI)
- Risk dashboard of own advisees with High / Medium / Low levels, filters and search
- Student profile with AI reasons, course performance and risk trend
- Suggested action for each student
- AI-drafted message (editable) to contact the student
- Intervention log and history

### Admin Console
- Manage users (students, teachers, advisors, admins)
- Create courses with teacher and class schedule; enroll students
- Assign students to advisors
- Run AI risk scoring and view model results

### AI Engine
- Feature extraction from attendance, marks and submissions
- Rule-based baseline score + **logistic regression** risk model
- Explainable reasons for every prediction
- Rule-based suggested actions
- Message drafting with the **Groq LLM API** (only anonymous reasons are sent, never names or IDs), with a template fallback

---

## Technology Stack

| Layer | Technology |
|---|---|
| Frontend | React.js (Vite), JavaScript, HTML, CSS, Tailwind CSS, React Router, Axios, Recharts |
| Backend | Python, Django, Django REST Framework (token authentication) |
| Database | PostgreSQL |
| AI / ML | pandas, NumPy, scikit-learn (logistic regression), joblib |
| AI Integration | Groq API (LLM) for advisor message drafting |
| Deployment | Vercel (frontend), Render (backend and database) |
| Tools | Git, GitHub, VS Code, Postman, Jupyter Notebook |

---

## System Overview

```
 Student / Teacher / Advisor / Admin
                │
                ▼
   React frontend  (localhost:5173)
                │  JSON + login token
                ▼
   Django REST API (localhost:8000/api) ──────► Groq LLM API
                │                                (advisor message only)
                ▼
   PostgreSQL database  ◄──── AI module (ai/)
                               weekly risk scoring:
                               features → model → reasons → action
```

---

## Repository Structure

```
Uniclass-AI/
├── frontend/        React app (pages, components, API calls)       – Frontend
├── backend/         Django REST API (accounts, courses, grades, advising) – Backend
├── database/        ER diagram, table notes, sample SQL, backups   – Database
├── ai/              Feature extraction, model training, scoring, LLM message – AI
├── docs/            API document, designs, screenshots, report
├── .gitignore
└── README.md
```

Each folder has its own `README.md` describing what goes inside.

---

## Getting Started

> The project is in its initial stage. Setup steps will be completed as development progresses.

**Requirements:** Node.js (LTS), Python 3.12, PostgreSQL 16, Git

```bash
# 1. Clone the repository
git clone https://github.com/SakibHasanAnik/Uniclass-AI.git
cd Uniclass-AI

# 2. Backend
cd backend
python -m venv venv
venv\Scripts\activate          # Windows  (macOS/Linux: source venv/bin/activate)
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver

# 3. Frontend (new terminal)
cd frontend
npm install
npm run dev
```

---

## Development Workflow

- Each member works on their own branch: `frontend-dev`, `backend-dev`, `db-ai-dev`
- Changes are merged into `main` through pull requests reviewed by the team leader
- Passwords, API keys and `.env` files are never committed

---

## Project Timeline (14 Weeks)

| Weeks | Phase |
|---|---|
| 1 – 2 | Planning, UI design, ER diagram, API list |
| 3 – 4 | Database, project setup, authentication |
| 5 – 7 | Core LMS: courses, materials, assignments, marks, attendance |
| 8 – 11 | Dashboards, AI model, risk scoring, advisor portal, AI message |
| 12 – 13 | Testing, bug fixing, deployment |
| 14 | Final report, presentation and demo |

---

## License

This project is developed for academic purposes as part of CSE4104 at Northern University of Business and Technology, Khulna.
