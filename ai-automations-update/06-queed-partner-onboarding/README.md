# 06 · Queed: Installation Partner Onboarding (Claude + n8n)

A working prototype that onboards a new installation partner for **Queed** (smart electricity meters, Saudi Arabia) with no manual copy-pasting. Built as an answer to *"How would you automate the onboarding of a new installation partner?"*

▶️ **2-minute walkthrough:** [Loom link]

## What happens when a partner applies

```
Partner fills form (EN/AR labels)
        │
        ▼
Deterministic checks ─── CR = 10 digits · VAT = 15 digits starting/ending in 3
        │                 Saudi mobile normalised to 9665XXXXXXXX · missing documents by partner type
        ▼
Claude assesses ──────── score 0–100 · Tier A/B/C · risks · questions for the call · priority
        │                 (fails safe: unreadable output → "REVIEW", never auto-approve)
        ▼
Google Drive ─────────── partner folder + "00 - Onboarding summary"
ClickUp ──────────────── task with application, AI assessment and onboarding checklist
Slack ────────────────── alert in #partner-onboarding with score, risks and links
Email (+ WhatsApp) ───── welcome in the partner's language, listing exactly what's missing
        │
        ▼ (if documents missing)
Wait 48h → still "waiting on documents" in ClickUp? → reminder email + Slack nudge

Weekly (Sunday 9:00 Riyadh): Slack report of new applications by tier, city and type,
plus partners ready for review and partners stuck on documents.
```

## Design decisions

- **AI where judgement is needed, code where accuracy is needed.** Format checks and missing documents are computed in code. Claude only scores fit, flags risks and suggests questions for the call.
- **Messages come from approved templates, not free AI text.** Every partner gets accurate, consistent wording. Arabic templates are drafts to be approved once by a native speaker on Queed's team, then they run automatically.
- **Prompt-injection safe.** Applicant text is passed to Claude as data inside `<application>` tags, and the system prompt tells Claude to flag (not follow) instructions in it. See test case 3.
- **ClickUp is the source of truth.** Ops changes the task status when documents arrive; the reminder and the weekly report read that status.

## Files

| File | What it is |
|---|---|
| `workflows/partner-onboarding.json` | Main workflow (18 nodes) |
| `workflows/weekly-report.json` | Weekly Slack report |
| `prompts/partner-assessment-system-prompt.txt` | Claude system prompt and scoring rubric |
| `test-cases.md` | Three test applications to run |

## Setup (about 15 minutes)

1. In n8n: **Workflows → Import from file** for both JSON files.
2. Create credentials:
   - **Header Auth "Anthropic"**: name `x-api-key`, value your Anthropic API key → select it on *Claude: assess partner*.
   - **Header Auth "ClickUp"**: name `Authorization`, value your ClickUp personal token (`pk_...`) → select it on all ClickUp HTTP nodes.
   - **Google Drive**, **Slack** and **Gmail** OAuth credentials on their nodes.
3. Replace placeholders: `REPLACE_WITH_PARTNERS_FOLDER_ID` (Drive) and `REPLACE_WITH_CLICKUP_LIST_ID` (both workflows).
4. In the ClickUp list, add the statuses **waiting on documents** and **ready for review**.
5. Create Slack channel `#partner-onboarding` and invite the n8n app.
6. Check the model name in *Build Claude request* against the current [Claude models list](https://docs.claude.com/en/docs/about-claude/models/overview).
7. For a live demo, set *Wait 48 hours* to 1 minute. Activate, open the form URL, submit a test case.

## Assumptions to confirm with Queed

- Required documents per partner type (in *Normalize & pre-check*).
- Priority cities and the scoring rubric (in the system prompt).
- Whether WhatsApp Business API is available (node included, disabled by default; first outbound message needs a Meta-approved template).

## Next steps for production

Native ClickUp checklists and assignees, document upload in the form with file checks, CRM sync of approved partners, partner-portal account creation via the development partner's API, and an Arabic-language Slack summary if the ops team prefers.
