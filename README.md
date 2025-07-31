# 🔁 Lead Qualification Workflow – n8n Automation Challenge

## 👤 Candidate: Akona Ciko
## Role Applied: n8n Automation Engineer
## Company: REM Waste
## Submission Date: 31-07-2025

🧠 Objective
To design an n8n automation that captures, validates, scores, stores, and routes incoming leads using free-tier tools — optimizing internal response and follow-up for high-value opportunities.

⚙️ Tech Stack
n8n (Self-hosted): Automation workflow builder

Google Sheets (or Airtable): Lead storage

Gmail SMTP: Email notifications

Wait Node: Simulates lead nurturing follow-up timing

🔧 Workflow Overview
1. 📥 Simulate Lead Submission
A Set node creates dummy test data that mimics a marketing form with fields:
full_name, email, phone, company_size, budget, interest_level

2. 🧠 Lead Scoring Logic
A Code node processes the lead data and scores each lead:

Hot: Budget > 5000 and Interest = "High"

Warm: Budget > 2000 or Interest = "Medium"

Cold: All others

Missing required fields throw a validation error.

3. 🔍 Is Lead Qualified (Hot)?
An IF node checks if the lead is Hot:

If true → trigger alert and follow-up

If false → store quietly in a spreadsheet (optional)

4. 📨 Notify Team: New Hot Lead
An SMTP email is sent instantly to alert the team of a Hot lead with budget and interest details.

5. ⏱️ Delay Before Follow-Up
A Wait node pauses the workflow for 2 minutes to simulate delay/nurture.

6. 🔁 Follow-Up: Lead Nurture
A second email is sent as a follow-up or approval prompt, nudging internal action.

📝 Assumptions
All input data is simulated via a Set node

Google Sheet or Airtable schema includes all mapped fields

SMTP credentials are already configured

This test does not include UI-based form integration (e.g., Tally.so)

📎 Files Delivered
n8n_workflow_export.json: Importable n8n workflow (via drag & drop)

n8n_workflow_diagram.pdf: Visual structure of the complete workflow

README.md: This documentation for reviewer context

✅ Notes
This automation demonstrates real-world logic and rapid deployment of internal tooling via low-code. It can be easily extended with webhook triggers, third-party APIs (CRM, Slack, WhatsApp), or AI scoring logic.

