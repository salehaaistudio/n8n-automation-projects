Heliora Solar --- AI Lead & Appointment Automation

An n8n automation system that processes solar inquiries, retrieves
property-level solar insights when available, sends tailored customer
emails, syncs leads to HubSpot, and manages Google Calendar consultation
confirmations and 10-minute reminders.

What it does
1. Solar lead intake and estimate
- Receives customer details through an n8n webhook.
- Validates name, email, phone, address, and consent.
- Geocodes the property address and checks that it resolves to a US
  location.
- Calls Google Solar API to retrieve roof solar potential.
- Calculates an indicative panel count, system size, annual energy
  estimate, and estimated annual energy value when usable API data is
  returned.
- Uses a clearly labelled illustrative fallback when property-specific
  solar data is unavailable.
- Uses OpenAI to create a short customer-friendly introduction.
- Sends a tailored solar estimate email and creates or updates the
  lead in HubSpot.
- Alerts the team when address review or email-failure handling is
  needed.
2. Appointment confirmation
- Detects new Google Calendar bookings.
- Retrieves event and attendee details.
- Sends a confirmation email to the customer when their email is
  found, and sends an admin notification.
3. 10-minute appointment reminders
- Detects newly created calendar events.
- Calculates the reminder time as 10 minutes before the appointment.
- Waits until the reminder time, then fetches the event again.
- Checks that the event is still confirmed, the start time has not
  changed, and a Google Meet link is available.
- Sends reminder emails to the customer and admin.
Main integrations
- n8n
- Google Solar API
- Google Maps Geocoding API
- HubSpot CRM
- OpenAI (GPT-4o mini)
- Gmail
- Google Calendar

Key workflow capabilities
- Webhook-based lead intake
- Input validation and conditional routing
- Address geocoding and US-location validation
- Solar API integration and estimate/fallback handling
- AI-assisted customer email copy
- CRM contact create/update
- Customer and admin email notifications
- Calendar event parsing and meeting-link extraction
- Scheduled reminders with event re-validation

Important estimate disclaimer
Google Solar API results are treated as preliminary roof estimates. The
workflow labels fallback figures as illustrative references rather than
property-specific results. Final system design, production, utility
rates, savings, and pricing require verification.
Setup notes
1. Import the workflow JSON into n8n.
2. Configure your own credentials for Google Maps, Google Solar API,
   HubSpot, OpenAI, Gmail, and Google Calendar.
3. Replace admin email addresses and booking links with the client's
   values.
4. Configure webhook URLs and test both verified-estimate and fallback
   paths.
5. Test customer email extraction, CRM field mapping, calendar booking,
   rescheduled/cancelled events, and reminder delivery before
   production use.
   
Security
Do not publish workflow exports containing API keys, access tokens,
credential IDs, private email addresses, or other client information.
Store secrets in n8n credentials or environment variables, and rotate
any key that has been exposed in a shared export.
Project status
This README describes the workflow structure in the supplied n8n JSON
export. It does not independently certify production deployment, live
API access, or end-to-end delivery. Test all integrations with
client-owned credentials before presenting the system as
production-ready.
