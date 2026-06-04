# Client Onboarding & Follow-up (Zapier)

A Zapier automation that handles new-client onboarding end to end: it captures a submission, records the client in a CRM, prepares a welcome email for review, schedules a follow-up, and alerts the team.

## Problem solved
Onboarding a new client usually means several manual steps across email, calendar, and a CRM. This Zap chains them together while keeping a human in the loop for the actual email.

## Architecture
1. **Webhook intake** receives the new-client submission.
2. **Normalize & validate** the email address.
3. **Create an Airtable CRM record** for the client.
4. **Create a Gmail DRAFT** — a welcome email is drafted, **not auto-sent** (kept for human review).
5. **Schedule a Google Calendar follow-up** two days out.
6. **Send a Telegram alert** to notify the team.

## Tools
Zapier · Airtable · Gmail · Google Calendar · Telegram.

## Files
- `case-study.html` — case-study page with screenshots and the step-by-step architecture.

## Limitations & honesty notes
- **No machine-readable export:** Zapier has no public export format, so this folder documents the Zap via the case-study page and this README rather than an importable file.
- **Disabled after proof:** the Zap was built and verified, then **turned off** — it is not live.
- **Draft, not send:** the Gmail step only creates a draft; nothing is emailed automatically.
- **Demo data:** the records shown are sample data, not real clients.
