# Student Registration Automation with n8n\n\n## Overview\nA workflow that receives student regi
strations, stores them in Google Sheets, and sends an automatic confirmation email.\n\n## Proble
m\nManual registration handling takes time and can lead to missed or incorrectly recorded inform
ation.\n\n## Workflow\n1. n8n Form Trigger receives a submission.\n2. Google Sheets appends the
registration as a new row.\n3. Gmail sends a confirmation email to the student.\n\n## Tools\n- n
8n\n- Google Sheets\n- Gmail\n\n## Repository contents\n- `workflows/`: exported n8n workflow JS
ON\n- `screenshots/`: workflow and test evidence\n- `docs/`: setup and testing notes\n\n## Setup
\n1. Create your own Google Sheet with the required column headings.\n2. Import the JSON workflo
w into your n8n workspace.\n3. Create your own Google Sheets and Gmail credentials in n8n.\n4. S
elect your spreadsheet and map the fields if needed.\n5. Test with sample data before activating
the workflow.\n\n## Testing\nDescribe the tests you performed and include screenshots of succes
sful runs.\n\n## Security\nNo credentials, tokens, private student data, or secrets are included
in this repository
