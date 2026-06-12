# Flow — Tasks & Time

A single-file todo + calendar + study timer PWA, themed in charcoal & dark blue.

## Deploy (GitHub Pages)
1. Create a repo, push `index.html`, `manifest.json`, `icon.png`.
2. Settings → Pages → deploy from main branch.
3. Open the page in Safari on iPhone → Share → **Add to Home Screen**.

Everything (tasks, types, sessions, plans, keys) is stored in your browser's localStorage on the device — nothing disappears on refresh. Note: it's per-device/per-browser, so the home-screen app keeps its own data.

## OpenRouter AI (Plan tab + poster scan)
1. Get a key at openrouter.ai → paste into Settings → AI.
2. Default model is `anthropic/claude-sonnet-4.5`; the poster scan needs a vision-capable model (the default works).

## Google Calendar sync
A static site can't hide credentials, so you use your own free OAuth client:
1. console.cloud.google.com → New project → enable **Google Calendar API**.
2. OAuth consent screen → External → add yourself as a test user.
3. Credentials → Create credentials → **OAuth Client ID** → Web application.
   - Authorized JavaScript origins: `https://YOURNAME.github.io`
4. Copy the Client ID into Settings → Google Calendar → Connect.
5. All your calendars appear: checkboxes control what's *shown*; the radio button picks the **one** calendar this app *writes* to (tasks, scanned events).

## How the timer eats budgets
Running a task's ▶, the stopwatch, or pomodoro are all the same engine. Finish a session → the focused time is logged to that day's study total and subtracted from the task's time budget. When the budget hits zero you're prompted to mark it done. Pomodoro breaks aren't counted.
