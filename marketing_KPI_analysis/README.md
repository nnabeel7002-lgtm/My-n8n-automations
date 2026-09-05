# 📊 Marketing KPI Analysis

An n8n workflow that analyzes marketing campaign data from Google Sheets using OpenAI and generates an automated performance report via Gmail.

## 🔄 Workflow Architecture

`Manual Trigger` ➔ `Google Sheets` ➔ `Calculate KPIs` ➔ `OpenAI Analysis` ➔ `Markdown` ➔ `Gmail`

## ✨ Features

- 📊 **Marketing KPI calculation:** Processes raw data into actionable metrics.
- 📈 **Traffic Analysis:** Evaluates clicks and impressions.
- 🎯 **Conversion Analysis:** Tracks successful user actions.
- 💰 **Spend & Cost Analysis:** Monitors campaign expenditure.
- 📉 **Rate Calculation:** Computes Click-Through Rate (CTR) and Cost Per Click (CPC).
- 🤖 **AI-Powered Insights:** Deep-dive marketing analysis using OpenAI.
- 💡 **Automated Recommendations:** Actionable steps to improve future campaigns.
- ⭐ **Performance Score:** Grades campaigns out of 10 based on efficiency.
- 📧 **Email Report Generation:** Sends formatted insights directly to your inbox.

## 📥 Input

The workflow reads marketing campaign data directly from a connected Google Sheet.

**Example Sheet Structure:**

| Campaign | Clicks | Impressions | Conversions | Spend |
|----------|--------|-------------|-------------|-------|
| Q3 Promo | 1200   | 50000       | 45          | $300  |

### 🧮 Calculated KPIs
Before passing data to the AI, the workflow calculates the following aggregates and metrics:
- Total Clicks
- Total Impressions
- Total Conversions
- Total Spend
- Click-Through Rate (CTR)
- Cost Per Click (CPC)
- Conversion Rate
- Cost Per Conversion

### 🤖 AI Analysis
Using the structured metrics, the OpenAI model generates:
- **Executive Summary**
- **KPI Evaluation**
- **Recommendations**
- **Performance Score out of 10**

## 📤 Output

The generated marketing analysis is formatted natively using Markdown and automatically emailed as a clean, professional report via Gmail.

## 🛠️ Technologies

- **n8n:** Workflow automation and routing.
- **OpenAI:** Data analysis and natural language generation.
- **Google Sheets:** Data storage and source.
- **Gmail:** Report delivery.
- **JavaScript & Markdown:** Data processing, calculations, and email formatting.

## ⚙️ Setup Instructions

1. **Import** the workflow JSON into your n8n instance.
2. **Connect Credentials:** Add your own credentials for Google Sheets, OpenAI, and Gmail.
3. **Configure Source:** Select your Google Sheet containing the marketing data in the Google Sheets node.
4. **Configure Destination:** Set the recipient email address in the Gmail node.
5. **Run:** Execute the workflow manually or set up a schedule trigger.

> **⚠️ Note:** Credentials are not included in this workflow. You must configure and authenticate your own accounts after importing.

## 🎯 Purpose

This project was built to practice marketing analytics, KPI calculations, AI-powered analysis, Google Sheets integration, and automated email reporting within the n8n ecosystem.