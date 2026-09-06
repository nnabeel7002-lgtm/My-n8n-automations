# 📸 Instagram Leads Generation

An n8n automation that collects Instagram business profiles, uses a local AI model to qualify potential leads, prevents duplicate leads, stores qualified leads in Google Sheets, and sends Discord notifications for HOT leads.

## 🔄 Workflow

```text
Instagram Data
      ↓
HTTP Request
      ↓
AI Lead Analyzer
      ↓
Validate & Parse
      ↓
Check for Duplicate
      ↓
Already Exists?
   ↙          ↘
 YES           NO
  ↓             ↓
 STOP        Valid Lead?
                ↓
             HOT / WARM
             ↙       ↘
           HOT       WARM
            ↓          ↓
       Google Sheets  Google Sheets
            ↓
      Discord Alert 🔥

## ✨ Features

- 📸 **Instagram profile data collection**
- 🤖 **AI-powered lead qualification**
- 🔥 HOT / 🟡 WARM / ❄️ COLD **classification**
- 🔍 **JSON validation and parsing**
- ♻️ **Duplicate lead detection**
- 📊 **Google Sheets lead storage**
- 🔔 **Discord notifications for HOT leads**
- 🧠 **Local AI using Ollama**
- 🔐 **API credentials kept outside the workflow**

## 🧠 AI Lead Qualification

### The AI analyzes:
- Username
- Full name
- Biography
- Business category
- Followers
- Following
- Business account status
- Number of posts

### It classifies each profile as:
- 🔥 **HOT:** Strong evidence that the business could benefit from automation, AI, software, or digital services.
- 🟡 **WARM:** Potentially relevant business, but there is no strong evidence of an immediate need.
- ❄️ **COLD:** Unlikely to be a potential customer.

## 📊 Output

Qualified leads are stored in Google Sheets with the following columns:
- Username
- Full Name
- Business
- Industry
- Interest
- Lead Quality
- Reason
- Instagram URL

> **Note:** 🔥 **HOT** leads additionally trigger a Discord notification containing the lead information.

## ♻️ Duplicate Detection

Before a lead is processed further, the workflow searches the Google Sheet using the Instagram Username.

- **If the username already exists:** Already Exists → **STOP**
- **If the username is new:** New Lead → **Continue → Qualification → Storage**

*This prevents the same Instagram account from being added repeatedly.*

## 💻 Technologies Used

- **n8n** (Workflow Automation)
- **Ollama** (Local LLM hosting)
- **Llama 3.2 1B** (AI Model)
- **Instagram Data Scraper/API**
- **HTTP Request**
- **Google Sheets API**
- **Discord API**
- **JavaScript**

## 🚀 Setup Instructions

1. **Import** the workflow JSON into n8n.
2. **Configure** your Instagram data/API source. Add your own Apify/API credentials.
3. **Connect Ollama:** Configure your Ollama connection and make sure `llama3.2:1b` is available locally.
4. **Setup Google Sheets:** Connect your Google Sheets account and create a Google Sheet with the required columns mentioned above.
5. **Setup Discord:** Configure your Discord bot and channel webhooks.
6. **Update Credentials:** Replace the placeholder values in the imported workflow with your own configuration.
7. **Run:** Execute the workflow!

> ⚠️ **Important:** API keys, Discord bot tokens, Google Sheet IDs, and other private credentials are intentionally not included in this repository. Configure your own credentials after importing the workflow.

## 🎯 Purpose

This project was built to practice AI-powered lead generation, API integration, data validation, deduplication, Google Sheets automation, Discord notifications, and local LLM integration using n8n and Ollama.
