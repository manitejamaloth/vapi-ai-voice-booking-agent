# AI Voice Booking Agent — Vapi + n8n

An AI-powered voice booking assistant that handles customer calls, checks appointment availability, books detailing services through Google Calendar, and automatically records and summarizes completed calls.

## 🎯 Problem

Handling appointment bookings manually can be time-consuming for service businesses. Customers may call outside business hours, staff have to check calendar availability manually, and booking details can be missed or entered incorrectly.

This project automates the booking process using an AI voice agent while keeping the workflow connected to the business's existing calendar and communication tools.

## ⚙️ How It Works

1. **Customer Call**: A customer calls the AI voice agent powered by Vapi.
2. **Service Selection**: The agent identifies the customer's preferred detailing service.
3. **Availability Check**: The agent checks Google Calendar for available appointment times.
4. **Booking**: After confirming the customer's preferred time, the appointment is created automatically in Google Calendar.
5. **Call Data Extraction**: Structured booking information such as email, date, time, and service type is extracted from the call.
6. **Call Summarization**: The completed call transcript is sent to an LLM through n8n to generate a concise summary.
7. **Record Keeping**: Booking details and the call summary are stored in Google Sheets.
8. **Confirmation**: A confirmation message/email is automatically sent to the customer.

## 🚗 Supported Services

- Full Interior Detailing
- Full Exterior Detailing
- Full Interior & Exterior Detailing

## 🛠️ Tools Used

- **Vapi** — AI voice agent and call handling
- **n8n** — Workflow orchestration and automation
- **Google Calendar** — Appointment availability and booking
- **Google Sheets** — Booking and call record storage
- **Gmail** — Customer confirmation
- **OpenAI API** — Call summarization and AI processing

## 📸 Workflow Screenshot
![n8n Workflow ](https://github.com/manitejamaloth/vapi-ai-voice-booking-agent/blob/8005d847277c768283cefac7ee97798d37d9ec8d/01-n8n-workflow.png)

## 📸 Voice Assistant Configuration Screenshot
![Vapi Assistant Configuration](https://github.com/manitejamaloth/vapi-ai-voice-booking-agent/blob/0993353cab748b76800b664c9e53a324a9f96e23/02-vapi-assistant.png)

## 📄 Workflow Export

Full workflow JSON available in this repo — see [workflow.json](https://github.com/manitejamaloth/vapi-ai-voice-booking-agent/blob/0993353cab748b76800b664c9e53a324a9f96e23/Vapi%20End%20of%20Call%20Report.json).

## 🔄 Workflow Architecture

```text
Customer Call
      ↓
   Vapi AI Agent
      ↓
Service Selection
      ↓
Google Calendar
(Check Availability)
      ↓
Confirm Appointment
      ↓
Google Calendar
(Create Event)
      ↓
   End of Call
      ↓
   n8n Webhook
      ↓
Extract Booking Data
      ↓
Generate AI Summary
      ↓
Google Sheets
      ↓
Gmail Confirmation
