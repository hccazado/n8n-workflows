# n8n Automation Workflows

Production workflows built with n8n and Node.js for real client projects. No tutorials — these run in production.

---

## What's in here

### 01 · WhatsApp Appointment Confirmation — agende API

Clinics using the agende platform needed to send WhatsApp confirmations, but patients with multiple appointments on the same day were getting multiple separate messages. Confusing and unprofessional.

This workflow aggregates all same-day appointments per patient into a single message before sending. It runs on a cron schedule, crawls professional profiles via dynamic ID sequences, groups appointments in memory by phone number, and dispatches one clean message per patient.

**Stack:** n8n · Node.js · agende API · WhatsApp Business API

---

### 02 · Appointment Confirmation — Feegow Clinic

Feegow is a clinic management platform used across Brazil. This workflow replaces a manual confirmation process: it queries the Feegow API on a schedule, normalizes the appointment and patient data, and sends out confirmation notifications automatically.

Handles timezone-aware scheduling for `America/Sao_Paulo`, partial failure tolerance so one bad record doesn't kill the whole run, and dynamic query parameters per polling cycle.

**Stack:** n8n · Node.js · Feegow API

---

### 03 · Multi-Resource Availability Engine — Google Calendar + uChat

Booking systems that only check one calendar break the moment you add a second resource (a second room, a second professional, shared equipment). This workflow solves that.

It runs parallel Google Calendar queries across multiple resource calendars, cross-references the busy/free windows, and only returns slots where everything is genuinely available. Supports custom exception intervals for holidays and blocked periods.

Deployed for multiple clients as the backend powering Google Calendar integration inside uChat — letting them manage their entire appointment schedule directly through their WhatsApp flows without touching the calendar manually.

**Stack:** n8n · Node.js · Google Calendar API · uChat

---

## Common patterns across all workflows

- Batch loops with throttling to avoid hitting API rate limits
- In-memory data transformation via custom Node.js execution blocks
- `continueRegularOutput` error handling so partial failures don't block the pipeline
- Automated retry logic on transient failures

---

## Using these workflows

Import the `.json` file from any folder directly into your n8n instance. Each folder has its own README with setup steps and required credentials.