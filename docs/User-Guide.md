# User Guide

## Overview

The **Lead Capture → Google Sheets → Telegram** workflow automatically captures incoming lead information through a webhook, stores it in Google Sheets, and instantly notifies your team via Telegram.

This workflow is designed for small businesses, agencies, freelancers, and anyone who needs a lightweight lead management solution without building a custom backend.

---

# Workflow Summary

Incoming Lead
↓
Webhook
↓
Validation
↓
Data Normalization
↓
Google Sheets
↓
Telegram Notification
↓
Success Response

---

# Features

- Receive leads using a REST API
- Validate required fields
- Normalize incoming data
- Store leads in Google Sheets
- Send instant Telegram notifications
- Return a JSON success response
- Easy to customize
- No coding required after setup

---

# Expected Input

The workflow expects a POST request with JSON.

Example:

```json
{
    "name": "John Doe",
    "email": "john@example.com",
    "phone": "+94771234567",
    "company": "ABC Pvt Ltd",
    "message": "Need automation for my business"
}
```

---

# Expected Output

```json
{
    "success": true,
    "message": "Lead captured successfully"
}
```

---

# How It Works

## Step 1

A client application sends a POST request to the webhook.

↓

## Step 2

The workflow validates the incoming request.

↓

## Step 3

Lead data is normalized into a consistent format.

↓

## Step 4

The lead is appended as a new row in Google Sheets.

↓

## Step 5

A Telegram notification is sent to the configured chat.

↓

## Step 6

The API returns a success response.

---

# Typical Use Cases

- Website contact forms
- Landing pages
- Marketing campaigns
- CRM lead collection
- Internal business tools
- Automation demonstrations
- Portfolio projects
- Learning n8n workflows

---

# Best Practices

- Use HTTPS in production.
- Protect the webhook with authentication if exposed publicly.
- Regularly back up your Google Sheet.
- Store credentials securely.
- Enable workflow execution logging for troubleshooting.

---

# Customization Ideas

You can easily extend this workflow by adding:

- Email notifications
- Slack notifications
- Airtable integration
- HubSpot CRM
- Salesforce
- OpenAI lead qualification
- AI lead scoring
- Auto email replies
- File attachments
- Database storage

---

# Support

If you encounter issues:

1. Verify credentials.
2. Confirm webhook URL.
3. Check workflow execution logs.
4. Review the Configuration Guide.

---

# License

This workflow is released under the MIT License.