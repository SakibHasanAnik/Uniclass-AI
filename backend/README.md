# Backend

**Owner:** Arnab Basu (models: Sakib Hasan Anik)

Django REST API that serves the React frontend.

**Tech:** Python, Django, Django REST Framework, PostgreSQL

| Folder | Contents |
|---|---|
| `config/` | Project settings and main URLs |
| `accounts/` | Users, roles, login, admin login, logout |
| `courses/` | Courses, schedule, enrollment, materials, assignments, submissions |
| `grades/` | Assessments, marks, attendance, analytics, dashboards |
| `advising/` | Advisor-student links, risk scores, interventions, AI message |
| `advising/management/commands/` | `seed_data` and `score_students` commands |
| `media/` | Uploaded files (not committed) |

All endpoints start with `/api/`. The full list is in `docs/api.md`.
The Django project files (`manage.py`, `requirements.txt`, etc.) will be added during setup in week 3.
