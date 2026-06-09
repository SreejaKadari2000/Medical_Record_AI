# 🏥 MedRecord AI — Automated Medical Record Review Pipeline

 **Reducing paralegal review time from 3–5 hours to under 20 minutes per case using OCR + LLM automation.**


## Overview

Medical record review is the most persistent bottleneck in personal injury law. Between client sign and settlement, paralegals routinely spend **3–5 hours per case** manually reading, organizing, and summarizing medical PDFs — before an attorney ever touches the file.

**MedRecord AI** is an n8n automation pipeline that eliminates this bottleneck. It ingests raw medical PDFs delivered via email, runs them through a multi-stage OCR and LLM pipeline (Mistral + Claude), and produces:

- ✅ A structured **medical chronology** with dates, providers, diagnoses, and treatments
- ✅ A one-page **attorney-ready case summary** in plain English
- ✅ Automatic logging to **Google Sheets** for case tracking and QA

The system integrates directly into existing case management infrastructure (e.g., Captorra) and requires no custom software installation on the firm's end.

---

## 🎯 Problem Statement

| Pain Point | Current State | With MedRecord AI |
|---|---|---|
| Review time per case | 3–5 hours paralegal time | < 20 minutes automated |
| Consistency | Varies by paralegal | Standardized output every time |
| Case bottleneck | Delays settlement timeline | Near-instant turnaround |
| Scalability | Linear with headcount | Scales with case volume |
| Data capture | Siloed in PDFs | Structured, queryable, logged |

For a firm handling 50+ cases/month, this pipeline can recover **150–250 paralegal hours monthly** — hours that can be redirected to higher-value legal work.

---

## 🔧 Workflow Architecture

```
Gmail Trigger
    │
    ▼
Get Message (email + attachments)
    │
    ▼
Upload PDF to Mistral (OCR)
    │
    ▼
Get Signed URL → Poll for OCR Results
    │
    ▼
Data Cleaning (JSON normalization)
    │
    ▼
Claude (LLM) — Structured Chronology + Case Summary
    │
    ▼
Google Sheets — Append Results
```

<img width="1568" height="559" alt="image" src="https://github.com/user-attachments/assets/3ef1b7aa-6688-4899-9564-1edb42c0ea9a" />

