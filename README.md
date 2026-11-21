# Student Registration Automation with n8n

An n8n workflow that captures student course registrations, saves them to Google Sheets, and sends each student an automatic confirmation email.

## Overview

When a student submits the registration form, the workflow records their details in a spreadsheet and confirms receipt by email. No manual data entry is needed.

## The Problem

Handling registrations by hand is slow and error-prone. Details get mistyped, submissions get missed, and students wait for a reply. This workflow removes those steps and gives every student an instant acknowledgement.

## How It Works

1. **Form Trigger:** n8n hosts a registration form and starts the workflow on each submission.
2. **Google Sheets:** the submission is appended as a new row.
3. **Gmail:** a confirmation email is sent to the address the student provided.

### Form fields

| Field | Type | Required |
|---|---|---|
| Full Name | Text | Yes |
| Email | Email | Yes |
| Course | Dropdown (English, Python, Data Science) | Yes |
| Preferred Schedule | Dropdown | No |

## Tools

- [n8n](https://n8n.io)
- Google Sheets
- Gmail

## Repository Contents

| Folder | Contents |
|---|---|
| `workflows/` | The exported n8n workflow (JSON) |
| `screenshots/` | Workflow and test evidence |
| `docs/` | Setup and testing notes |

## Setup

1. **Create a Google Sheet** with a tab named `Registrations` and these column headings in row 1:
   `Submitted At`, `Full Name`, `Email`, `Course`, `Preferred Schedule`
2. **Import the workflow:** in n8n, choose *Import from File* and select the JSON file from `workflows/`.
3. **Add credentials:** create your own Google Sheets and Gmail credentials in n8n.
4. **Connect your sheet:** open the Google Sheets node, select your spreadsheet, and check the field mapping.
5. **Test before going live:** submit sample data using the form's test URL, then activate the workflow once everything works.

## Testing

Describe the tests you ran, for example:

- A valid submission creates a new row in the sheet.
- The confirmation email arrives at the address entered in the form.
- A submission with a missing required field is rejected by the form.

Add screenshots of successful runs to the `screenshots/` folder and link them here.

## Security

This repository contains no credentials, tokens, secrets, or real student data. The workflow export has been cleaned of account identifiers. You must supply your own credentials and spreadsheet when you import it. Use fictional data when testing.
