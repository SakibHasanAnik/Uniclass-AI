# Frontend

**Owner:** Sarder Fariha Alam Trishna

React (Vite) app for all four roles: student, teacher, advisor and admin.

**Tech:** React, JavaScript, HTML, CSS, Tailwind CSS, React Router, Axios, Recharts

| Folder | Contents |
|---|---|
| `src/api/` | All calls to the Django API (one file per area) |
| `src/context/` | Logged-in user, role and token |
| `src/routes/` | Role-based route protection |
| `src/components/` | Reusable layout, UI, cards, tables, charts, forms |
| `src/pages/auth/` | Login (`/login`) and admin login (`/adminlogin`) |
| `src/pages/student/` | Student dashboard and course pages |
| `src/pages/teacher/` | Teacher dashboard, courses, marks, attendance, analytics |
| `src/pages/advisor/` | Advisor risk dashboard, student profile, interventions |
| `src/pages/admin/` | Admin dashboard, users, courses, advisors, AI scoring |
| `src/hooks/`, `src/utils/` | Small helpers |
| `src/assets/`, `public/` | Images, logo, icons |

The Vite project files (`package.json`, `vite.config.js`, etc.) will be added during setup in week 3.
