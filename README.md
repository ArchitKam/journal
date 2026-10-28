# Journal

A private, offline-first journal and daily task list. Runs on iPhone and Mac as a home-screen app.
Data lives on each device and syncs to a Google Sheet you own.

## Setup (already done)
- **Storage:** a Google Sheet named "Journal" (tabs `Journal` and `Tasks`) with an attached Apps Script
  (`apps-script/`, kept local only) deployed as a web app. Requests must carry a secret key.
- **Hosting:** this repo, served by GitHub Pages.
- **Devices:** open the site → iPhone: Safari → Share → Add to Home Screen; Mac: Safari → File → Add to Dock.
  Then in the installed app: Settings → paste the sync code → Save & sync.

## How it works
- **Journal:** tap a date on the calendar. Each day asks your six questions; "Something to tell
  someone?" opens one more. Dots mark days you wrote.
- **Tasks:** tasks you don't finish carry over to the next day, with ↻N showing days carried
  (gold at 3+, red at 7+). ··· → Move to tomorrow / Delete. Future dates let you plan ahead.
- **Sync:** saves locally on every keystroke and syncs a couple of seconds later, whenever the app
  opens, and every minute. Works offline and catches up when back online. If two devices edit the
  same day's entry, the most recent edit wins.
- **Your data:** the Sheet has a `Journal` tab and a `Tasks` tab, one row each. Settings also has
  "Download backup".

## Updating the app
Edit files, push to GitHub, and bump `CACHE` in `sw.js` (e.g. `journal-v2`). Devices pick up
the new version on the next launch after that.
