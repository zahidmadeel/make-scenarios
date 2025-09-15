# 1 — Create Google Calendar events from data on your Google Sheet

Summary
- Watches rows in a Google Sheet and creates Google Calendar events for each row.
- Supports multiple attendees (space-separated email list in the attendees column).
- Blueprint file: `1-Create Google Calendar events from data on your Google Sheet.blueprint.json`

Sanitization / placeholders
Replace these placeholders in the blueprint before importing:
- <SPREADSHEET_ID> — your Google Sheet ID/file
- <SHEET_NAME> — sheet/tab name (e.g., "Sheet1")
- <GOOGLE_CONN_ID> — Make connection id for the Google account used for Calendar/Sheets
- <GOOGLE_RESTRICTED_ACCOUNT_ID> — Make connection id used for sending emails (restricted)
- <YOUR_EMAIL> — calendar ID / primary email
- <YOUR_NAME> — sender display name in email templates

Sheet column mapping (headers expected in the blueprint)
- Column A (start date) — Start date/time
- Column B (end date) — End date/time
- Column C (event name) — Event summary
- Column D (attendees) — Space-separated emails (e.g., "a@example.com b@example.com")
- Columns E–Z — optional, used for description or other fields in the blueprint

How to use
1. Update the blueprint JSON placeholders with your IDs and connection names.
2. In Make (make.com):
   - Import the blueprint JSON as a new scenario.
   - Authorize/attach the referenced Google connections (google, google-restricted).
   - Ensure the sheet has headers and the header row range matches the blueprint (A1:Z1).
3. Run a test by adding a sample row to the watched sheet and execute the scenario.

Testing tips
- Use a test calendar and test email addresses you control.
- Start with limit = 1 and feeder values small to validate behavior before scaling.

Privacy
- This blueprint in the repo is sanitized. Never commit live credentials, tokens, or private user data.

If you want, add a sample CSV or a screenshot of the sheet structure to this docs file.