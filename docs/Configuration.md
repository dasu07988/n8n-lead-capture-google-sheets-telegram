# Configuration Guide

## Overview

This guide explains how to configure the **Lead Capture → Google Sheets → Telegram** workflow after importing it into n8n.

---

# Required Credentials

The workflow requires two credentials:

1. Google Sheets
2. Telegram Bot

---

# Google Sheets Configuration

## Step 1

Create a new Google Spreadsheet.

Spreadsheet Name:

Lead Capture Database

Worksheet Name:

Leads

---

## Step 2

Create the following columns:

| Name | Email | Phone | Company | Message | Created At |

The column names must match exactly.

---

## Step 3

Create Google Sheets credentials in n8n.

Supported authentication:

- Google OAuth2
- Google Service Account

If using a Service Account:

- Enable Google Sheets API
- Enable Google Drive API
- Share the spreadsheet with the Service Account email
- Give Editor permission

---

## Step 4

Open the **Save Lead** node.

Configure:

Resource:
Sheet Within Document

Operation:
Append Row

Select:

Document:
Lead Capture Database

Sheet:
Leads

Map the columns:

Name → name

Email → email

Phone → phone

Company → company

Message → message

Created At → created_at

Save the node.

---

# Telegram Configuration

## Step 1

Open Telegram.

Search:

@BotFather

Create a new bot.

Save the Bot Token.

---

## Step 2

In n8n create a new Telegram credential.

Enter:

Access Token:
<Your Bot Token>

Base URL:

https://api.telegram.org

Save the credential.

---

## Step 3

Open your bot.

Press:

Start

or send:

/start

---

## Step 4

Retrieve your Chat ID.

Open:

https://api.telegram.org/bot<YOUR_TOKEN>/getUpdates

Locate:

chat.id

Example:

123456789

---

## Step 5

Open the **Notify Team** node.

Configure:

Chat ID:
Your Chat ID

Message:

Uses dynamic lead information automatically.

---

# Webhook Configuration

Open the **Receive Lead** node.

Method:

POST

Example endpoint:

http://localhost:5678/webhook-test/lead-capture

When deployed:

https://your-domain/webhook/lead-capture

---

# Testing

Run the workflow.

Send the following JSON:

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "+94771234567",
  "company": "ABC Pvt Ltd",
  "message": "Need automation for my business"
}
```

Expected Result:

✅ New row added to Google Sheets

✅ Telegram notification received

✅ Success response returned

---

# Troubleshooting

## Google Sheet not found

Possible causes:

- Google Drive API disabled
- Google Sheets API disabled
- Spreadsheet not shared with Service Account
- Wrong spreadsheet selected

---

## Telegram message not received

Check:

- Bot Token
- Chat ID
- Bot started
- Telegram credential

---

## Empty Telegram fields

Verify:

- Normalize Lead node
- Field mapping
- Expressions

---

## Webhook returns an error

Check:

- HTTP Method = POST
- Workflow is active
- Response mode configuration
- Test URL vs Production URL

---

# Configuration Complete

Your workflow is now ready for production use.