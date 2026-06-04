# automation-systems

Backend automation systems by **Yigitcan Ük** (Vienna). This repository documents three working automations built on no-/low-code platforms, with sanitized exports and case-study pages as evidence. Tone: evidence over hype.

> **Demo-data notice:** Every record, name, and email visible in the exports and case studies is **demo/sample data**, not real client data. All secrets — webhooks, tokens, Telegram chat IDs, Airtable base/table/user IDs, and credential/connection IDs — were replaced with placeholders (`<...>`) before commit.

## Projects

| Folder | System | Stack | Status |
|--------|--------|-------|--------|
| [`n8n/`](n8n/) | AI Lead Intake CRM | n8n · Airtable · Telegram · webhook | Local/self-hosted build · demo data · sanitized export |
| [`make/`](make/) | Daily Operations Report | Make · Airtable · Telegram | Built · 09:00 schedule intentionally inactive · demo data |
| [`zapier/`](zapier/) | Client Onboarding & Follow-up | Zapier · Airtable · Gmail · Google Calendar · Telegram | Built, then disabled after proof · demo data · no machine export |

## What's inside each folder
- **n8n/** — sanitized workflow JSON (main + error handler) and a case-study page.
- **make/** — sanitized blueprint JSON and a case-study page.
- **zapier/** — case-study page + step-by-step architecture (Zapier has no public export format).

## Conventions
- Secrets are never committed; all exports are sanitized first.
- Each project README states the problem solved, the architecture, the tools, and honest limitations.

See [`CLAUDE.md`](CLAUDE.md) for the repository rules and the verified facts these docs are based on.
