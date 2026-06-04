# Daily Operations Report (Make)

A Make scenario that produces a daily operations summary from the same Airtable data the n8n lead pipeline writes to, and delivers it as a Telegram message.

## Problem solved
The owner needs a quick daily snapshot — how many leads came in, how many were duplicates, how many were missing an email, and how many workflow errors occurred — without opening Airtable and counting by hand.

## Architecture
1. **Read** Airtable `Leads_clean` and `Automation_Logs`.
2. **Aggregate** the records and **count event types**: new leads, duplicate attempts, missing-email submissions, and workflow errors.
3. **Send a Telegram summary** with the totals and basic system checks.

Built from Airtable search modules, aggregators, and a Telegram send module.

## Tools
Make · Airtable · Telegram.

## Files
- `daily-operations-report.blueprint.json` — scenario blueprint (sanitized).
- `case-study.html` — case-study page with screenshots and walkthrough.

## Limitations & honesty notes
- **Intentionally inactive:** a 09:00 daily schedule is configured, but the scenario is **deliberately left inactive** — it is not running.
- **Sanitized blueprint:** Airtable base/table IDs, the Airtable user ID, the Telegram chat ID, and Make connection IDs are replaced with placeholders (`<...>`). To run it you must reconnect your own Airtable and Telegram connections.
- **Demo data:** the figures are computed from sample data, not real client activity.
- **Fixed template:** the Telegram summary uses a fixed message template.
