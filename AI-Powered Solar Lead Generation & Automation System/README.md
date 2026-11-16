# ☀️ Heliora Solar LeadFlow

**AI-Powered Solar Lead Generation & Automation System**

Heliora Solar LeadFlow is an intelligent automation system designed to streamline solar lead management, validate US property addresses, deliver automated customer emails, manage CRM records, and simplify appointment scheduling.

## 🚀 Key Features

- **US Address Validation:** Rejects invalid addresses and addresses outside the United States.
- **Automated Lead Processing:** Processes valid customer submissions and delivers automated email responses.
- **Solar Estimation:** Uses Google Solar API to retrieve property-specific solar information when available.
- **CRM Integration:** Automatically stores customer information in HubSpot CRM.
- **Appointment Booking:** Allows customers to schedule meetings with the admin.
- **Booking Notifications:** Sends confirmation emails to customers and meeting notifications to the admin.
- **Fallback Email System:** Sends customers an email when roof-specific solar data cannot be verified.
- **Manual Lead Review:** Notifies the admin to manually review unverified addresses and contact potential customers.
- **Email Failure Alert:** Notifies the admin if a customer email cannot be delivered.

## 🔄 Workflow Overview

### 1. Valid Address
- Validates the submitted US property address.
- Retrieves available solar information.
- Sends the customer an automated solar estimate email.
- Saves customer information in HubSpot CRM.
- Provides an appointment booking option.

### 2. Appointment Booking
- Customer schedules a meeting with the admin.
- Customer receives a booking confirmation email.
- Admin receives a meeting notification.

### 3. Address Verification Failure
- Sends the customer a fallback email.
- Provides an option to schedule a meeting.
- Sends an admin alert for manual address verification.
- Keeps customer information available in CRM for follow-up.

### 4. Customer Email Failure
- Detects customer email delivery failure where supported by the email workflow.
- Sends an alert to the admin for manual review.

## 🛠️ Tech Stack

| Technology | Purpose |
|---|---|
| n8n | Workflow Automation |
| Google Solar API | Solar Data Retrieval |
| Google Maps Geocoding API | Address Geocoding |
| HubSpot CRM | Lead Management |
| Gmail | Automated Email Notifications |
| Google Calendar | Appointment Scheduling |
| AI | Intelligent Content Generation |

## 🎯 Project Goal

**No Missed Leads. Smarter Automation. Better Customer Experience.**

The goal is to ensure that every customer submission receives an appropriate response, while the admin is notified when manual intervention is required.

## ⚙️ Automation Architecture

Customer Form → Address Validation → Solar Data Retrieval → Email Automation → HubSpot CRM → Appointment Booking → Notifications

Fallback Route:

Address/Solar Verification Failure → Customer Fallback Email → Admin Review Alert → CRM Follow-up

## 🔐 Security

- API credentials should be stored securely.
- Never expose API keys, access tokens, or private customer information.
- Use secure webhook endpoints.
- Configure appropriate access permissions for connected services.

## 👩‍💻 Project

**Project Name:** Heliora Solar LeadFlow

**Category:** AI Automation | Lead Generation | CRM Automation

**Automation Platform:** n8n

---

*Built to make solar lead management smarter, faster, and more reliable.*
