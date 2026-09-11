# AIVOA AI Complaint QMS

An AI-powered Customer Complaint Management System designed for pharmaceutical manufacturing and quality assurance workflows.

The system converts unstructured customer complaints from text or documents into structured complaint records, performs AI-assisted risk assessment and analysis, supports targeted corrections through an AI Copilot, and enables human-reviewed commitment to a QMS Ledger.

## 🚀 Features

- AI-powered complaint information extraction
- Support for complaint text and document uploads
- PDF, DOCX, TXT and EML document processing
- Structured pharmaceutical complaint form
- AI Copilot for complaint corrections and questions
- Targeted field updates while preserving unrelated information
- Complaint completeness assessment
- Risk and severity assessment
- Duplicate complaint detection
- Root-cause and CAPA recommendations
- Complaint summary generation
- Human-in-the-loop review before QMS commitment
- Immutable/read-only state after commitment
- PostgreSQL persistence
- Audit event tracking
- LangGraph-based workflow orchestration
- Groq LLM integration
- REST API using FastAPI
- React + Redux frontend

---

## 🏗️ System Architecture

```text
Customer Complaint
       │
       ├── Text Input
       │
       └── PDF / DOCX / TXT / EML
                │
                ▼
        React + Redux Frontend
                │
                ▼
          FastAPI REST API
                │
                ▼
        Document/Text Parser
                │
                ▼
           LangGraph
       Intake & Copilot Workflow
                │
                ▼
          Groq LLM
                │
                ▼
     Structured Complaint Fields
                │
        ┌───────┼────────┐
        ▼       ▼        ▼
   Completeness Risk   Duplicate
        │       │        │
        └───────┼────────┘
                ▼
          QA Review
                │
                ▼
       Human Confirmation
                │
                ▼
         QMS Ledger Commit
                │
                ▼
          Read-only Record
                │
                ▼
           PostgreSQL
