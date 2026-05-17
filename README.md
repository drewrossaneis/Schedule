# Schedule. — Calendar Facilitator

A browser-based tool that reads a team schedule spreadsheet and converts each person's shifts into a calendar file they can import directly into Google Calendar or Apple Calendar.

No installation. No server. Everything runs locally in the browser.

---

## What it does

Team schedules are often shared as spreadsheets with everyone's shifts together — hard to read, especially on mobile. This tool lets each person extract only their own shifts and add them to their personal calendar in a few clicks.

- Reads the schedule exported as CSV
- Filters shifts by the person's first name
- Generates a `.ics` file ready to import into any calendar app
- Marks work shifts (🟢) and days off (🔴)
- Handles overnight shifts that cross midnight correctly

---

## How to use

1. Open the schedule spreadsheet and export the current month's tab as **CSV**
2. Open the tool in any browser — no installation needed
3. Upload the CSV file
4. Type your first name exactly as it appears in the Name column
5. Click **Generate Calendar**
6. Download the `.ics` file and import it into your calendar

---

## Reimporting when the schedule changes

Calendar apps do not update existing events on reimport — they add duplicates. To update cleanly:

1. Delete your **Work Schedule** calendar
2. Create a new one with the same name
3. Import the new `.ics` file

---

## Calendar setup

### Google Calendar
- Go to [calendar.google.com](https://calendar.google.com)
- Click `+` next to "Other calendars" → **Create new calendar** → name it **Work Schedule**
- Settings → **Import & Export** → Import → select the `.ics` → choose **Work Schedule**
- Syncs automatically to the Google Calendar app on your phone

### Apple Calendar
- **Mac:** `File → New Calendar` → name it **Work Schedule** — choose iCloud so it syncs to your iPhone
- **Mac import:** double-click the `.ics` file → Calendar asks which calendar → choose **Work Schedule**
- **iPhone import:** tap the `.ics` file → Calendar asks where to add it → choose **Work Schedule**
- Syncs automatically to all Apple devices on the same Apple ID

---

## Spreadsheet format

The tool expects a CSV exported from a spreadsheet with this structure:

- Separator: `;` (semicolon)
- A `Surname` / `Name` row marks the start of each weekly block
- Date row with values like `4-May`
- Time zone rows: `Greek time` and `Brazil time` — the tool uses **Brazil time only**
- `start` and `end` columns under each time zone
- Value `off` marks a day off

---

## Privacy

Nothing is sent to any server. All processing happens locally in your browser. The CSV file never leaves your device.

---

## Tech

Plain HTML, CSS, and JavaScript. No frameworks, no dependencies, no build step. Open the `.html` file in any browser and it works.
