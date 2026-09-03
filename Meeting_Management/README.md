# Meeting Management Automation with n8n

An automated meeting management system built with **n8n**, **JotForm**, **Google Sheets**, and **Gmail**.

This project automates the process of creating, updating, cancelling, tracking, reminding, and archiving meetings while maintaining meeting records in Google Sheets.

---

## 🚀 Project Overview

The system receives meeting information through a JotForm submission and processes it automatically using n8n workflows.

It supports:

- Creating new meetings
- Updating existing meetings
- Cancelling meetings
- Validating attendee email addresses
- Detecting scheduling conflicts
- Sending meeting reminders
- Automatically marking completed meetings as `Done`
- Generating weekly meeting summaries
- Archiving completed and cancelled meetings

---

## 🛠️ Technologies Used

- **n8n** – Workflow automation
- **JotForm** – Meeting information collection
- **Google Sheets** – Meeting database and record management
- **Gmail** – Automated email notifications
- **JavaScript** – Data processing and logic

---

## 📂 Workflows

### 1. Meeting Management

**File:** `Meeting_Management.json`

The main workflow responsible for processing meeting requests.

It handles:

- Add Meeting
- Update Meeting
- Cancel Meeting
- Attendee email validation
- Duration parsing
- Conflict detection
- Google Sheets record management

### Workflow Structure

```text
JotForm
   ↓
Email Validation
   ↓
Duration Parser
   ↓
Edit Fields
   ↓
Operation Routing
   ├── Add Meeting
   │      ↓
   │  Conflict Detection
   │      ↓
   │  Append Row
   │
   ├── Update Meeting
   │      ↓
   │  Find Meeting
   │      ↓
   │  Update Row
   │
   └── Cancel Meeting
          ↓
       Find Meeting
          ↓
       Update Status
```

---

### 2. Reminder Workflow

**File:** `Reminder_Workflow.json`

Automatically checks meeting records and identifies scheduled meetings that require reminders.

The workflow is designed to:

```text
Schedule Trigger
      ↓
Get Meetings
      ↓
Check Scheduled Meetings
      ↓
Send Reminder Email
```

---

### 3. Auto-Done Workflow

**File:** `Auto_Done_Workflow.json`

Automatically updates meeting records when meetings are completed.

Basic workflow:

```text
Schedule Trigger
      ↓
Get Meetings
      ↓
Find Completed Meetings
      ↓
Update Status
      ↓
Done
```

---

### 4. Weekly Digest

**File:** `Weekly_Digest.json`

Generates a weekly summary of meeting activity.

The workflow calculates:

- Total meetings
- Scheduled meetings
- Completed meetings
- Cancelled meetings

It then generates a summary that can be sent through Gmail.

Example:

```text
Weekly Meeting Summary

Total Meetings: 10
Scheduled: 4
Done: 5
Cancelled: 1
```

---

### 5. Archive Workflow

**File:** `Archive_Workflow.json`

Moves completed and cancelled meetings into a separate Archive sheet.

The workflow identifies meetings with statuses such as:

- `Done`
- `Cancelled`

and moves their records to the archive.

```text
Schedule Trigger
      ↓
Get Meetings
      ↓
Find Archive Candidates
      ↓
Append to Archive Sheet
```

---

## 📊 Google Sheets Structure

The main meeting sheet contains the following fields:

| Column | Description |
|---|---|
| Title | Meeting title |
| Attendees | Names of attendees |
| Attendees_Gmails | Attendee email addresses |
| Gist | Meeting description |
| Status | Current meeting status |
| ID | Unique meeting identifier |
| Date/Time | Scheduled date and time |
| Duration(mins) | Meeting duration |

An additional **Archive** sheet is used to store completed and cancelled meetings.

---

## 🔄 Meeting Operations

### Add Meeting

A new meeting is submitted through JotForm.

The workflow:

1. Receives the form submission.
2. Validates attendee emails.
3. Parses the meeting duration.
4. Checks for scheduling conflicts.
5. Adds the meeting to Google Sheets if no conflict exists.

### Update Meeting

An existing meeting can be modified using its unique ID.

The workflow:

1. Receives the meeting ID.
2. Searches Google Sheets.
3. Checks whether the meeting exists.
4. Updates the corresponding row.

### Cancel Meeting

A meeting can be cancelled using its ID.

The workflow:

1. Finds the meeting.
2. Verifies that it exists.
3. Updates its status to `Cancelled`.

---

## 🧠 Conflict Detection

Before adding a meeting, the workflow checks existing meeting records to determine whether a scheduling conflict exists.

A buffer is used between meetings to help prevent overlapping or closely scheduled meetings.

If a conflict is detected, the meeting is not added normally.

---

## 📧 Email Automation

Gmail is used for automated communication, including:

- Meeting reminders
- Weekly meeting summaries
- Other meeting-related notifications

---

## ⚙️ How to Import the Workflows

To use these workflows in another n8n instance:

1. Open n8n.
2. Create or open a workflow.
3. Select the workflow options menu.
4. Choose **Import from File**.
5. Select the required `.json` workflow file.
6. Reconnect the required credentials.
7. Configure the Google Sheets and Gmail credentials.
8. Test the workflow.

> **Important:** Credentials and API keys are not included in the exported workflow files. They must be configured separately in n8n.

---

## 🔐 Security

Do not upload sensitive credentials to this repository.

Never commit:

- API keys
- Passwords
- OAuth tokens
- Webhook secrets
- Private credentials
- `.env` files containing secrets

Use n8n's credential management system instead.

---

## 📁 Repository Structure

```text
Meeting-Management-Automation/
│
├── Meeting_Management.json
├── Reminder_Workflow.json
├── Auto_Done_Workflow.json
├── Weekly_Digest.json
├── Archive_Workflow.json
└── README.md
```

---

## 🎯 Learning Objectives

This project demonstrates practical use of n8n for:

- Workflow automation
- Webhook/form integrations
- Conditional logic
- Data transformation
- JavaScript Code nodes
- Google Sheets integration
- Email automation
- Scheduled workflows
- Record management
- Error handling
- Business process automation

---

## 📌 Future Improvements

Possible improvements include:

- Better date/time handling
- More advanced conflict detection
- Google Calendar integration
- Improved email templates
- Automatic attendee invitations
- Error notification workflows
- More detailed analytics
- Dashboard integration

---

## 👩‍💻 Author

**Nabeeha Nabeel**

Built using n8n as an automation project.
