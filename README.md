# cargo-van-calculator
Cargo Van Load Calculator

## Lead sourcing n8n workflow (with Twilio)
This repo includes an n8n workflow you can import to capture inbound leads, enrich them, log qualified/unqualified leads, and send a Twilio SMS follow-up. The workflow JSON lives at `workflows/lead-sourcing-with-twilio.json` and expects credentials for Airtable and Twilio to be configured in n8n. Company enrichment uses the free OpenCorporates API (no credentials required for basic usage). The webhook endpoint is `POST /webhook/lead-sourcing-intake` with fields like `name`, `email`, `phone`, `company`, and `domain`.

### Downloading the workflow JSON
To download the workflow file for import into n8n, copy it from the repo with:

```bash
cp workflows/lead-sourcing-with-twilio.json ./lead-sourcing-with-twilio.json
```
