# API Contract

All endpoints start with `/api/`. This file will be completed in week 2.

| Area | Endpoints |
|---|---|
| Auth | `POST /auth/login`, `POST /auth/admin-login`, `POST /auth/logout`, `GET /auth/me` |
| Courses | `/courses`, `/courses/:id`, `/courses/:id/materials`, `/courses/:id/assignments` |
| Grades | `/courses/:id/assessments`, `/assessments/:id/marks`, `/courses/:id/attendance`, `/courses/:id/analytics` |
| Dashboards | `/student/dashboard`, `/teacher/dashboard` |
| Advisor | `/advisor/students`, `/advisor/students/:id`, `/advisor/students/:id/message`, `/advisor/students/:id/interventions` |
| Admin | `/admin/users`, `/admin/courses`, `/admin/advisors/:id/students`, `/admin/ai/run` |
