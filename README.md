# cargo-van-calculator
Cargo Van Load Calculator

## Lead sourcing n8n workflow (with Twilio)
This repo includes an n8n workflow you can import to capture inbound leads, enrich them, log qualified leads, and send a Twilio SMS follow-up. The workflow JSON lives at `workflows/lead-sourcing-with-twilio.json` and expects credentials for Clearbit, Airtable, and Twilio to be configured in n8n. The webhook endpoint is `POST /webhook/lead-sourcing-intake` with fields like `name`, `email`, `phone`, `company`, and `domain`.
