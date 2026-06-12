# Flow v3

Single-file PWA: tasks + calendar + study timer + AI day plans.

## Deploy
Push `index.html`, `manifest.json`, `icon.png` to GitHub Pages. Open in Safari → Add to Home Screen.
Data lives in localStorage (per device; the home-screen app has its own storage — set up inside it).

## Google Calendar (multi-account)
Settings → paste your OAuth Client ID → "+ Connect a Google account". Repeat for more accounts.
- First connected account = **Main**: tasks & scanned events write to the calendar you pick (radio).
- Other accounts are view-only; checkboxes choose which calendars display.
- Access tokens are cached ~1h and refreshed silently while your Google session lives; if one expires fully, the account shows "Needs sign-in" with a Reconnect button.

## Plan
Set the day window (start → end) → Generate. Budgets are hard caps. Anything that can't fit shows in an orange feasibility card with a suggestion. Edit blocks manually, revise via AI, or Delete the plan.

## Gestures
- Tap a calendar day → day timeline slides up; swipe down (from top) or swipe right to close.
- Long-press any block/chip in the day view → Edit / Delete.
- All sheets (new task, settings, import) close with swipe-down.

## Paste import
Tasks tab → "Paste a list" → AI splits the text into tasks (dates, times, budgets, types). Without an API key, each line becomes a today-task.
