# Architecture

## Overview

The Lead Capture workflow follows a simple event-driven automation architecture.

It receives lead information through an HTTP webhook, validates the request, normalizes the data, stores it in Google Sheets, sends a Telegram notification, and finally returns a JSON response.

---

# High-Level Architecture

```

Client / Website
│
▼
Webhook (POST)
│
▼
Validate Lead
│
▼
Normalize Lead
│
├──────────────┐
│ │
▼ ▼
Google Sheets Telegram
│ │
└──────┬───────┘
▼
Respond to Webhook

```

---

# Components

## 1. Receive Lead

Purpose

Receives incoming HTTP POST requests.

Responsibilities

- Accept JSON payload
- Trigger workflow
- Pass data downstream

---

## 2. Validate Lead

Purpose

Ensures required fields are available.

Responsibilities

- Validate request
- Reject invalid data
- Prevent incomplete records

---

## 3. Normalize Lead

Purpose

Standardize the payload before processing.

Responsibilities

- Rename fields
- Clean input values
- Generate timestamp

Example Output

```json
{
  "name": "John Doe",
  "email": "john@example.com",
  "phone": "+94771234567",
  "company": "ABC Pvt Ltd",
  "message": "Need automation for my business",
  "created_at": "2026-07-19 11:20:00"
}
```

---

## 4. Google Sheets

Purpose

Persistent storage.

Responsibilities

- Append lead
- Preserve history
- Enable reporting

---

## 5. Telegram Notification

Purpose

Notify the team immediately.

Example

```

🚀 New Lead Received

Name: John Doe
Email: john@example.com
Phone: +94771234567

```

---

## 6. Respond to Webhook

Purpose

Return the API response.

Example

```json
{
    "success": true,
    "message": "Lead captured successfully"
}
```

---

# Data Flow

```

Client

↓

Webhook

↓

Validation

↓

Normalization

↓

Google Sheets

↓

Telegram

↓

API Response

```

---

# Technology Stack

| Component | Technology |
|-----------|------------|
| Workflow Engine | n8n |
| API | Webhook |
| Storage | Google Sheets |
| Notifications | Telegram Bot API |
| Data Format | JSON |

---

# Security Considerations

- Keep Telegram Bot Token secret.
- Restrict access to the webhook.
- Store credentials securely.
- Use HTTPS in production.
- Enable authentication for public deployments.

---

# Scalability

This workflow can be extended with:

- AI lead qualification
- CRM integration
- Email automation
- Database storage
- Analytics dashboards
- Slack or Microsoft Teams notifications
- Approval workflows
- Multi-step business processes

---

# Future Enhancements

Possible improvements include:

- Duplicate lead detection
- Rate limiting
- Email validation
- Phone number validation
- AI lead scoring
- CRM synchronization
- Audit logging
- Dashboard reporting
- Multi-user notifications

---

# Summary

The workflow follows a modular architecture where each node has a single responsibility. This makes the solution easy to maintain, extend, and reuse for future automation projects.