# 🚀 Lead Capture → Google Sheets → Telegram (n8n Workflow)

Automatically capture incoming leads via a webhook, store them in Google Sheets, and instantly notify your team through Telegram.

This workflow is designed for freelancers, agencies, startups, and businesses looking for a lightweight lead management automation built with **n8n**.

---

# ✨ Features

- 🌐 Receive leads through an HTTP Webhook
- ✅ Validate incoming requests
- 🔄 Normalize lead data
- 📊 Store leads in Google Sheets
- 📲 Send instant Telegram notifications
- ⚡ Return JSON API responses
- 🔧 Easy to customize
- 📦 Ready to import into n8n

---

# 📌 Workflow

```text
Client / Website
        │
        ▼
 Receive Lead (Webhook)
        │
        ▼
 Validate Lead
        │
        ▼
 Normalize Lead
        │
   ┌────┴────┐
   ▼         ▼
Google      Telegram
Sheets      Notification
   │         │
   └────┬────┘
        ▼
 Respond to Webhook
```

---

# 📁 Repository Structure

```text
Lead-Capture-GoogleSheets-Telegram
│
├── workflow/
│   └── lead-capture-google-sheets-telegram.json
│
├── docs/
│   ├── Installation.md
│   ├── Configuration.md
│   ├── User-Guide.md
│   └── Architecture.md
│
├── examples/
│   ├── sample-request.json
│   └── sample-response.json
│
├── screenshots/
│   ├── workflow-overview.png
│   ├── google-sheet-result.png
│   ├── telegram-notification.png
│   └── postman-test.png
│
├── README.md
├── LICENSE
├── CHANGELOG.md
└── requirements.md
```

---

# ⚙️ Requirements

- n8n
- Google Account
- Google Sheets
- Telegram Account
- Telegram Bot
- Google Sheets API
- Google Drive API

---

# 🚀 Quick Start

### 1. Clone the repository

```bash
git clone https://github.com/dasu07988/n8n-lead-capture-google-sheets-telegram.git
```

---

### 2. Import the workflow

Import:

```
workflow/lead-capture-google-sheets-telegram.json
```

into n8n.

---

### 3. Configure credentials

Configure:

- Google Sheets
- Telegram

Follow the guides inside the **docs** folder.

---

### 4. Execute

Send a POST request to the webhook.

Example:

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

# ✅ Example Response

```json
{
    "success": true,
    "message": "Lead captured successfully"
}
```

---

# 📷 Screenshots

Add screenshots here after exporting the workflow.

- Workflow Overview
- Google Sheets Result
- Telegram Notification
- Postman Test

---

# 📚 Documentation

Detailed documentation is available in the **docs** folder.

- Installation Guide
- Configuration Guide
- User Guide
- Architecture Guide

---

# 🛠️ Built With

- n8n
- Google Sheets API
- Telegram Bot API
- JSON Webhooks

---

# 💡 Future Improvements

- AI Lead Qualification
- Email Notifications
- Slack Integration
- Airtable Integration
- CRM Integration
- Duplicate Lead Detection
- Lead Scoring
- Dashboard Reporting

---

# 🤝 Contributing

Pull requests are welcome.

If you have suggestions for improvements, feel free to open an issue.

---

# 📄 License

This project is licensed under the MIT License.

---

# ⭐ Support

If you find this workflow useful, consider starring the repository.

It helps others discover the project.