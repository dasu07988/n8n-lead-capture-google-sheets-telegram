# Requirements

## Software

- n8n (Cloud or Self-hosted)
- Google Chrome (recommended)
- Postman (optional for testing)

---

## Accounts

- Google Account
- Telegram Account

---

## APIs

Enable the following APIs in Google Cloud:

- Google Sheets API
- Google Drive API

---

## Credentials

### Google Sheets

Choose one:

- Google OAuth2
- Google Service Account

If using a Service Account:

- Enable APIs
- Share the spreadsheet with the Service Account email
- Grant Editor permission

---

### Telegram

Requirements:

- Telegram Bot
- Bot Token
- Chat ID

---

## Spreadsheet

Spreadsheet Name:

Lead Capture Database

Worksheet:

Leads

Columns:

- Name
- Email
- Phone
- Company
- Message
- Created At

---

## Webhook

HTTP Method:

POST

Content-Type:

application/json

---

## Example Payload

```json
{
    "name":"John Doe",
    "email":"john@example.com",
    "phone":"+94771234567",
    "company":"ABC Pvt Ltd",
    "message":"Need automation for my business"
}
```

---

## Expected Response

```json
{
    "success": true,
    "message": "Lead captured successfully"
}
```

---

## Recommended Knowledge

Basic understanding of:

- n8n
- Webhooks
- Google Sheets
- Telegram Bots

No coding experience is required.