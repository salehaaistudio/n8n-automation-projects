# 🚀 WordPress & WooCommerce E-commerce Automation

An AI-powered e-commerce automation system built with **n8n, WooCommerce, Google Sheets, Gmail, and Google Gemini** to automate product management, order invoice processing, and weekly sales reporting.

## ✨ Key Features

### 1. 📦 WooCommerce Product Management
- Create, update, and delete WooCommerce products directly through Google Sheets.
- Automatically detect product actions using Google Sheets Trigger and Switch nodes.
- Manage product name, SKU, pricing, stock, status, and descriptions.
- Update Google Sheets after WooCommerce operations.

### 2. 🧾 AI-Powered Invoice Automation
- Retrieve WooCommerce order notification emails through Gmail.
- Extract customer and order information using Google Gemini AI Agent.
- Structure order data into customer name, order ID, sales amount, tax, and items sold.
- Automatically save extracted records in Google Sheets.

### 3. 📊 Automated Weekly Sales Reporting
- Run reports automatically using Schedule Trigger.
- Retrieve and aggregate sales records from Google Sheets.
- Analyze total orders, revenue, tax, and items sold using Google Gemini.
- Generate AI-powered executive summaries and business insights.
- Send formatted HTML sales reports through Gmail.

## 🔄 Workflow Architecture

**Workflow 1 — Product Management**

Google Sheets Trigger → Switch → WooCommerce Create / Update / Delete → Update Google Sheets

**Workflow 2 — Invoice Automation**

Gmail → AI Agent → Google Gemini → Structured Order Data → Google Sheets

**Workflow 3 — Weekly Sales Reporting**

Schedule Trigger → Google Sheets → Aggregate → AI Agent → Google Gemini → Gmail Report

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow automation |
| WordPress & WooCommerce | E-commerce platform |
| WooCommerce API | Product management |
| Google Sheets | Product and sales data storage |
| Gmail API | Order email processing and report delivery |
| Google Gemini | AI-powered data extraction and analysis |
| AI Agent | Intelligent processing and reporting |
| HTML & CSS | Email report formatting |

## 📸 Project Screenshots

The repository includes screenshots of:

1. WooCommerce Product Management Workflow.
2. Invoice Automation Workflow.
3. Weekly Sales Reporting Workflow.
4. Product Management Google Sheet.
5. Sales Records Google Sheet.
6. Automated Weekly Sales Email Report.

## ⚙️ Setup Requirements

- n8n instance
- WordPress website with WooCommerce
- WooCommerce API credentials
- Google Sheets and Gmail access
- Google Gemini API credentials

Configure the required credentials and permissions in n8n, connect the relevant nodes, and test each workflow using authorized store data.

## 🔐 Security

- Store API credentials securely inside n8n.
- Never publish API keys, tokens, passwords, or private webhook URLs.
- Use appropriate WooCommerce API permissions.
- Restrict access to connected Google accounts and spreadsheets.

## 🎯 Project Outcome

Built an integrated e-commerce automation system that simplifies WooCommerce product management, converts order emails into structured invoice records, and delivers AI-powered weekly sales reports with actionable business insights.

## 👩‍💻 Project Author

**Saleha Akter**  
Founder — **Saleha AI Studio**  
AI Automation Developer

## 📄 License

No open-source license has been specified. All rights reserved unless a license is added.
