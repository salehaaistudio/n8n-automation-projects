 🚀 n8n & AI-Powered E-Commerce & Invoice Automation Suite

Welcome to the n8n Automation Suite! This repository contains three production-ready, AI-enhanced workflow automations designed to streamline WordPress/WooCommerce operations, automated invoice extraction, and AI-driven weekly sales reporting.

📸 Workflow Overview & Technical Analysis

1. WordPress E-Commerce Product Management Automation (wordpress e-commers atumation)

This workflow automates product sync operations (Create, Update, Delete) between Google Sheets and WooCommerce.

[Google Sheets Trigger (rowAdded)] ➔ [Switch Node] ➔ [WooCommerce Node] ➔ [Google Sheets (Update row)]
                                         ├─ Create ──► Create Product
                                         ├─ Update ──► Update Product
                                         └─ Delete ──► Delete Product


Trigger: Google Sheets (rowAdded listener) — fires when a new row is appended.

Logic Routing: A Switch Node evaluates the operation rule (Create, Update, or Delete).

Action: Direct API execution on WooCommerce REST API for dynamic inventory management.

Feedback Loop: Updates the status back into Google Sheets to maintain data consistency.

Use Case: Bulk product catalog upload and automated CRUD synchronization without manual dashboard access.

2. AI-Powered Invoice Data Extraction (wordpress( invoice atumation))

An intelligent email processing pipeline that reads invoices/emails via Gmail, analyzes them using Google Gemini AI, and logs structured data into Google Sheets.

[Manual/Scheduled Trigger] ➔ [Gmail (Get Messages)] ➔ [AI Agent (Gemini Chat Model)] ➔ [Google Sheets (Append Row)]


Trigger: Manual trigger / Scheduled batch processing.

Data Retrieval: Gmail node (getMany: message) fetches raw invoice emails/data.

AI Engine: n8n AI Agent integrated with Google Gemini Chat Model extracts critical data fields (Vendor Name, Date, Line Items, Total Amount, Tax, etc.).

Output: Appends structured JSON output directly as new rows in Google Sheets.

Use Case: Zero-touch bookkeeping and automated data entry from raw emails to database.

3. Automated AI Sales Summary & Email Reporter (wordpress ( weekly sells report))

An automated reporting pipeline that periodically aggregates sales data, feeds it to an AI Agent to synthesize executive summaries, and broadcasts reports via Gmail.

[Schedule Trigger] ➔ [Google Sheets (Get Rows)] ➔ [Aggregate Node] ➔ [AI Agent (Gemini)] ➔ [Gmail (Send Message)]


Trigger: Cron/Schedule Trigger (e.g., Weekly on Mondays).

Data Ingestion: Reads weekly sales records from Google Sheets and passes them through an Aggregate Node.

AI Analysis: The AI Agent (powered by Google Gemini) analyzes key metrics, trends, revenue figures, and creates a concise text summary.

Distribution: Gmail node sends the formatted sales report automatically to stakeholders.

Use Case: Automated executive summary generation for e-commerce store managers.

🛠 Tech Stack & Tools Used

Automation Engine: n8n (Self-hosted / Cloud)

LLM Engine: Google Gemini Chat Model (via n8n LangChain integration)

Integrations: WooCommerce API, Gmail API, Google Sheets API

Workflow Nodes: Switch, Aggregate, AI Agent, Trigger nodes

⚙️ Installation & Setup

Prerequisites:

Installed n8n instance.

Google Gemini API Key.

WooCommerce REST API Consumer Key & Secret.

OAuth2 Credentials for Google Sheets & Gmail.

Importing Workflows:

Download the JSON workflow files from this repository.

Open your n8n canvas ➔ Click Import from File or paste JSON directly.

Configure Credentials:

Set up your Google Gemini API credentials under n8n Credentials section.

Connect your Google OAuth account for Gmail & Google Sheets.

Setup WooCommerce REST API credentials.

Activate: Toggle the workflow switch to Active.

💼 Resume Bullet Points (For your Portfolio)

You can copy and paste these metrics into your resume under Projects / Experience:

WooCommerce & AI Automation Suite: Designed and deployed end-to-end n8n workflows integrating WooCommerce, Google Sheets, and Google Gemini AI.

Automated Data Pipeline: Built an LLM-powered invoice parsing agent using Google Gemini to extract unstructured text from emails with structured output to Google Sheets.

E-Commerce Inventory Sync: Created dynamic CRUD automation connecting inventory spreadsheets directly to WooCommerce REST API using n8n rule-based logic.

AI Executive Reporting: Implemented scheduled cron jobs that aggregate weekly sales datasets and generate automated AI executive summary reports via Gmail.
