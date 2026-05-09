# 🗂️ Google Workspace Automations

Workflows that deeply integrate with Google Sheets, Gmail, Google Calendar, and Google Drive — enabling AI-assisted data management, scheduling, and cross-platform syncing.

---

## Workflows

### 1. Google Sheets Automation (AI Agent)
**Stack:** Agent → Google Calendar Tool (x4) → Gmail Tool → Memory Buffer  
An AI agent that uses Google Workspace as its toolset. Manages calendar events and drafts Gmail responses based on data pulled from Sheets — a full scheduling assistant built on top of Google's ecosystem.

### 2. Gmail HR Workflow
**Stack:** Schedule Trigger → HTTP Requests → Airtable → Set Nodes  
Automates HR email processing: fetches applicant or employee data on a schedule, syncs records to Airtable, and prepares structured data for downstream workflows.

### 3. AI Agent Calendar & Sheets Bot
**Stack:** Chat Trigger → Agent → Google Calendar Tools → Gmail Tool  
A conversational agent that manages your Google Calendar and Gmail through natural language. Ask it to book meetings, check availability, or send follow-ups — it handles the rest.

### 4. Google Calendar to Outlook Sync
**Stack:** Google Calendar Trigger → Event Transformation → Outlook Calendar  
Keeps Google Calendar and Outlook Calendar in sync in real-time. Handles event creation, updates, and cancellations bidirectionally across both platforms.

---

## Key Concepts Demonstrated
- Google Workspace API-level integration via n8n
- AI agents using Google tools natively
- Cross-platform calendar sync (Google ↔ Outlook)
- Scheduled HR data pipelines with Airtable
- Conversational interfaces over structured data
