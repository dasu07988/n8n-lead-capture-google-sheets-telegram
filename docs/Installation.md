# Installation Guide

## Overview

This guide explains how to install and run the **Lead Capture → Google Sheets → Telegram** workflow in n8n.

Estimated setup time: **5–10 minutes**

---

# Prerequisites

Before importing the workflow, make sure you have:

- n8n installed (Cloud or Self-hosted)
- Google Account
- Telegram Account
- Telegram Bot Token
- Google Sheets API enabled
- Google Drive API enabled

---

# Step 1 - Download the Workflow

Open the `workflow` folder and locate:

lead-capture-google-sheets-telegram.json

---

# Step 2 - Import into n8n

1. Open n8n
2. Click **Import from File**
3. Select:

lead-capture-google-sheets-telegram.json

4. Save the workflow

---

# Step 3 - Create Google Sheet

Create a spreadsheet named:

Lead Capture Database

Create a worksheet named:

Leads

Create the following headers:

| Name | Email | Phone | Company | Message | Created At |

---

# Step 4 - Create Telegram Bot

Open Telegram.

Search:

@BotFather

Create a new bot.

Save the Bot Token.

---

# Step 5 - Configure Credentials

Google Sheets

- Create Google Sheets credentials
- Connect your Google account (OAuth) or Service Account
- Select the spreadsheet

Telegram

Create a Telegram credential using your Bot Token.

---

# Step 6 - Activate Workflow

Save the workflow.

Click **Execute Workflow** for testing.

Once testing is successful, activate the workflow.

---

# Installation Complete

The workflow is now ready to receive incoming leads.