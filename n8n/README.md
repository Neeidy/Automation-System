# AI Lead Intake CRM (n8n)

An inbound-lead intake pipeline built in n8n: it receives lead submissions over a webhook, cleans and validates them, removes duplicates, stores them in Airtable, logs every outcome, notifies via Telegram, and routes failures to a dedicated error-handler workflow.

## Problem solved
Manual lead handling is slow and error-prone — duplicate entries, missing data, and no audit trail. This workflow normalizes incoming leads, rejects invalid/missing emails, prevents duplicates, and keeps a clean record plus an event log automatically.

## Architecture
1. **Webhook (POST)** receives the lead payload.
2. **Normalize** the submitted fields (visible in the export: name, email, phone, business type, city, message).
3. **Validate email** — missing/invalid emails take a dedicated response path.
4. **Deduplicate** against the `Leads_clean` table.
5. **Store**: new leads are written to `Leads_clean`; every outcome is written to `Automation_Logs`.
6. **Respond** on one of three paths: success / duplicate / missing-email.
7. **Notify** a new lead via **Telegram**.
8. A **separate error-handler workflow** captures failures and logs them to `Automation_Logs`.

Airtable base: **AI Lead CRM** · tables: **Leads_clean**, **Automation_Logs**.

## Tools
n8n (self-hosted) · Airtable · Telegram · HTTP webhook.

## Files
- `ai-lead-intake-crm.workflow.json` — main workflow (sanitized).
- `ai-lead-intake-crm.error-handler.json` — error-handler workflow (sanitized).
- `case-study.html` — case-study page with screenshots and walkthrough.

## Limitations & honesty notes
- **Sanitized export:** webhook path/ID, Airtable base/table IDs, Telegram chat ID, and n8n credential/instance IDs are replaced with placeholders (`<...>`). The JSON is **illustrative**, not drop-in importable — you must reconnect your own credentials and IDs.
- **Unauthenticated webhook:** the intake endpoint has no authentication in this build.
- **Local/self-hosted:** built on a self-hosted n8n instance, not n8n Cloud.
- **Demo data:** all visible lead records are sample data, not real clients.
