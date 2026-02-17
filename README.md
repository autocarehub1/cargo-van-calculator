# cargo-van-calculator
Cargo Van Load Calculator

## Sellable n8n workflows for San Antonio small businesses
This repo now includes six import-ready workflow JSON files for small businesses that want to improve response time, reduce admin work, and increase ROI through automation.

### 1) Lead sourcing + Twilio outreach
- **File:** `workflows/lead-sourcing-with-twilio.json`
- **Use case:** Capture inbound leads, qualify by score, log to Airtable, and trigger immediate SMS follow-up for hot leads.
- **Ideal clients:** Logistics, home services, legal intake, agencies.

### 2) Missed call text-back + lead capture
- **File:** `workflows/missed-call-text-back.json`
- **Use case:** When a call is missed, automatically send a text-back and log the lead so staff can recover the opportunity.
- **ROI angle:** Fewer missed opportunities and higher lead conversion from inbound phone traffic.

### 3) Appointment reminder + no-show recovery
- **File:** `workflows/appointment-reminder-and-no-show-recovery.json`
- **Use case:** Pull upcoming appointments hourly, send reminders, mark reminders as sent, and notify owners on no-show risk.
- **Ideal clients:** Med spas, clinics, salons, contractors, consultants.

### 4) Review request + reputation management
- **File:** `workflows/review-request-and-reputation-management.json`
- **Use case:** After job completion, request reviews from happy customers and alert team to recover poor experiences.
- **ROI angle:** Better Google review velocity + faster service recovery.

### 5) Invoice follow-up + payment reconciliation
- **File:** `workflows/invoice-follow-up-and-payment-reconciliation.json`
- **Use case:** Daily overdue invoice checks, payment reminder SMS, finance channel alerts, and reminder timestamp updates.
- **Ideal clients:** B2B services, field services, creative shops, small agencies.

### 6) New client onboarding automation
- **File:** `workflows/new-client-onboarding-automation.json`
- **Use case:** Trigger onboarding sequence via webhook, send welcome email + SMS, and notify internal team in Slack.
- **ROI angle:** Faster onboarding, reduced manual coordination, improved client experience.

## Import instructions
1. Open n8n and go to **Workflows** → **Import from File**.
2. Select one of the JSON files in `/workflows`.
3. Map credentials for each connected app (Twilio, Airtable, Slack, SMTP).
4. Update table names, channels, sender IDs, and copy as needed.
5. Activate once tested in your environment.

## Example lead intake payload (workflow #1)
The webhook endpoint is `POST /webhook/lead-sourcing-intake` with fields like `name`, `email`, `phone`, `company`, `domain`, and `score`.

```json
{
  "name": "Jordan Smith",
  "email": "jordan@example.com",
  "phone": "+15551234567",
  "company": "Example Logistics",
  "domain": "example.com",
  "score": 72,
  "source": "landing-page"
}
```

The Airtable `Leads` table should include the following fields:
- `Name` (single line text)
- `Email` (email)
- `Phone` (phone)
- `Company` (single line text)
- `Domain` (single line text)
- `Employees` (single line text or number; left blank by the workflow)
- `Source` (single line text)
- `Status` (single select: `Qualified`, `Unqualified`)
- `Score` (number)
