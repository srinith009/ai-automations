# 🤖 AI Automation Portfolio — n8n Workflows

A series of n8n automation builds covering patterns that come up in real automation work: AI agents with Claude and MCP, CRM and email pipelines, Google Workspace integrations, RAG systems and multi-agent setups. Folder `06` is a prototype built for a specific client brief (installation partner onboarding).

All workflows are built using **n8n** and integrate with tools like **Claude (Anthropic)**, **OpenAI**, **HubSpot**, **Google Workspace**, **Supabase**, **Slack**, and more.

---

## 📁 Repository Structure

| Folder | Description |
|--------|-------------|
| [`01-ai-agents-mcp`](./01-ai-agents-mcp/) | AI agents built with MCP (Model Context Protocol) and Claude |
| [`02-crm-email-automation`](./02-crm-email-automation/) | CRM data pipelines and AI-powered email workflows |
| [`03-google-workspace`](./03-google-workspace/) | Google Sheets, Gmail, and Calendar automations |
| [`04-rag-vector-db`](./04-rag-vector-db/) | Retrieval-Augmented Generation (RAG) systems with vector databases |
| [`05-multi-agent-systems`](./05-multi-agent-systems/) | Supervisor/worker multi-agent orchestration patterns |
| [`06-queed-partner-onboarding`](./06-queed-partner-onboarding) | Partner onboarding prototype: Claude scoring, ClickUp, Slack, Drive, bilingual emails, 48h reminders, weekly report |

---

## 🛠️ Tech Stack

- **Automation**: n8n (self-hosted)
- **AI Models**: Claude (Anthropic), OpenAI GPT-4o, DeepSeek R1
- **Protocols**: MCP (Model Context Protocol), REST APIs, Webhooks
- **CRM**: HubSpot, Airtable
- **Databases**: Supabase, PostgreSQL, MongoDB, Redis
- **Vector DBs**: ChromaDB, Supabase pgvector
- **Workspace**: Google Sheets, Gmail, Google Drive, Google Calendar
- **Messaging**: Slack, Telegram, Discord

---

## 🚀 How to Use

1. Clone this repository
2. Import any `.json` workflow file into your n8n instance via **Workflows → Import from file**
3. Configure credentials for the relevant services
4. Activate the workflow

---

## 📬 Contact

Built by **Katta Srinith Reddy** · [LinkedIn](https://www.linkedin.com/in/srinithkatta/)
