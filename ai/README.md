# AI Module

**Owner:** Sakib Hasan Anik (Team Leader)

Predicts which students may be at risk, explains why, suggests an action and drafts an advisor message.

**Tech:** pandas, NumPy, scikit-learn, joblib, Groq API

| File / Folder | Purpose |
|---|---|
| `features.py` | Builds one feature row per student from attendance, marks and submissions |
| `rules.py` | Rule-based baseline score |
| `train.py` | Trains the logistic regression model and saves metrics |
| `predict.py` | Score (0–100), level, top reasons and suggested action |
| `llm.py` | Groq message with template fallback |
| `models/` | Saved trained model |
| `data/` | Training data (synthetic) |
| `notebooks/` | Experiments |
| `results/` | Metrics and charts for the report |

**Pipeline:** database → features → model → score and level → reasons → suggested action → (on request) AI message

No names, IDs or emails are ever sent to the LLM.
