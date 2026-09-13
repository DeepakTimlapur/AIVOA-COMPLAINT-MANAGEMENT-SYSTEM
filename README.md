# AIVOA – AI-Powered Complaint Management System

An AI-powered Customer Complaint Management System designed for pharmaceutical manufacturing and Quality Assurance (QA) workflows.

AIVOA converts unstructured customer complaints from text or documents into structured complaint records, performs AI-assisted completeness, risk, and duplicate assessments, supports targeted corrections through an AI Copilot, and enables human-reviewed commitment to a QMS ledger.

---

## 🚀 Features

### 🤖 AI-Powered Complaint Processing
- Extracts structured complaint information from unstructured text and documents.
- Uses AI-assisted workflows for complaint analysis.
- Supports document-based complaint intake.

### 📋 Complaint Management
- Complaint registration and intake.
- Structured complaint records.
- Completeness assessment.
- Complaint risk assessment.
- Duplicate complaint detection.
- Complaint status and workflow management.

### 🧠 AI Copilot
- Provides targeted corrections and suggestions.
- Helps users identify incomplete or inconsistent complaint information.
- Supports human-in-the-loop review before final commitment.

### 🔍 Risk & Quality Analysis
- Rule-based and AI-assisted complaint evaluation.
- Risk categorization.
- Root-cause analysis support.
- CAPA recommendation support.

### 🏥 QMS Workflow
- Human-reviewed complaint commitment.
- QMS ledger workflow.
- Audit event tracking.
- Committed complaint records become read-only.

### 📊 Backend & Persistence
- REST APIs using FastAPI.
- PostgreSQL database support.
- SQLAlchemy ORM.
- Alembic database migrations.
- Structured audit logging.

---

## 🏗️ Technology Stack

### Frontend
- React
- TypeScript
- Redux
- Vite
- CSS

### Backend
- Python
- FastAPI
- SQLAlchemy
- Pydantic
- Alembic

### AI / Workflow
- LangGraph
- Groq API
- AI-assisted extraction and analysis

### Database
- PostgreSQL

### Testing
- Pytest
- Frontend test suite

---

## 📁 Project Structure

```text
AIVOA-Complaint-Management-System/
│
├── backend/
│   ├── app/
│   │   ├── services/
│   │   │   ├── analysis.py
│   │   │   ├── copilot.py
│   │   │   ├── documents.py
│   │   │   ├── groq.py
│   │   │   └── rules.py
│   │   │
│   │   ├── config.py
│   │   ├── database.py
│   │   ├── graphs.py
│   │   ├── main.py
│   │   ├── models.py
│   │   └── schemas.py
│   │
│   ├── alembic/
│   ├── tests/
│   ├── requirements.txt
│   └── .env.example
│
├── frontend/
│   ├── src/
│   │   ├── main.tsx
│   │   ├── store.ts
│   │   ├── style.css
│   │   └── tests
│   │
│   ├── index.html
│   ├── package.json
│   ├── pnpm-lock.yaml
│   └── tsconfig.json
│
├── docs/
│   ├── architecture.md
│   ├── demo-script.md
│   ├── interview-questions.md
│   └── qms-research.md
│
└── README.md


⚙️ System Architecture

                    ┌─────────────────────┐
                    │       User          │
                    └──────────┬──────────┘
                               │
                               ▼
                    ┌─────────────────────┐
                    │   React Frontend   │
                    │ React + Redux + Vite│
                    └──────────┬──────────┘
                               │ REST API
                               ▼
                    ┌─────────────────────┐
                    │    FastAPI Backend  │
                    └──────────┬──────────┘
                               │
             ┌─────────────────┼─────────────────┐
             │                 │                 │
             ▼                 ▼                 ▼
      ┌─────────────┐   ┌─────────────┐   ┌─────────────┐
      │ LangGraph   │   │ Groq / LLM  │   │ Rule Engine │
      │ Workflows   │   │ Analysis    │   │ Validation  │
      └──────┬──────┘   └─────────────┘   └─────────────┘
             │
             ▼
      ┌─────────────────────────────────┐
      │ Complaint Analysis              │
      │ • Extraction                    │
      │ • Completeness                  │
      │ • Risk Assessment               │
      │ • Duplicate Detection           │
      │ • AI Copilot                    │
      └──────────────┬──────────────────┘
                     │
                     ▼
              ┌───────────────┐
              │  PostgreSQL   │
              │   Database    │
              └───────┬───────┘
                      │
                      ▼
              ┌───────────────┐
              │ QMS / Audit   │
              │    Ledger     │
              └───────────────┘



              🔄 Complaint Processing Workflow
              Complaint Submitted
                      │
                      ▼
              Complaint Intake
                      │
                      ▼
              AI Information Extraction
                      │
                      ▼
              Completeness Assessment
                      │
                      ├── Incomplete ──► AI Copilot Suggestions
                      │                         │
                      │                         ▼
                      │                  Human Correction
                      │
                      ▼
              Risk Assessment
                      │
                      ▼
              Duplicate Detection
                      │
                      ▼
              Human Review
                      │
                      ▼
              QMS Commitment
                      │
                      ▼
              Audit Event
                      │
                      ▼
              Read-Only Committed Record
