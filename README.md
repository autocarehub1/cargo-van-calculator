# cargo-van-calculator
Cargo Van Load Calculator

## Lead sourcing n8n workflow (with Twilio)
This repo includes an n8n workflow you can import to capture inbound leads, log qualified/unqualified leads, and send a Twilio SMS follow-up. The workflow JSON lives at `workflows/lead-sourcing-with-twilio.json` and expects credentials for Airtable and Twilio to be configured in n8n. The webhook endpoint is `POST /webhook/lead-sourcing-intake` with fields like `name`, `email`, `phone`, `company`, `domain`, and `score`.

### Downloading the workflow JSON
To download the workflow file for import into n8n, copy it from the repo with:

```bash
cp workflows/lead-sourcing-with-twilio.json ./lead-sourcing-with-twilio.json
```

### Required data structures
Send the lead intake payload as JSON with these fields:

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
