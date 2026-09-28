# Daily Log — Calorie & Exercise Tracker

A single-file, no-frills calorie and exercise tracker built as a web app. No installs, no accounts, no build step — just open the HTML file in a browser.

## Why this exists

Most calorie-tracking apps are bloated. This one does exactly what's needed: log food and exercise, see net calories against a goal, and track weight over time — nothing else.

## Features

- **Daily log** — calorie gauge (net of exercise burnt), goal setting, meals split into Breakfast / Lunch / Dinner / Extra, daily weight entry, jump to any date.
- **Food library** — save foods as a fixed portion or by ingredients (with per-unit calories, so you specify how many of each ingredient you actually used when logging). Tag foods by meal and by your own custom categories (cuisine, source, food group, whatever you want). Search, filter, and sort.
- **Exercise library** — save exercises with a calories-burnt-per-hour rate and a Cardio / Weight training category. Same search/filter/sort as the food library.
- **History & progress** — days logged, foods/exercises saved, average net calories, tracking and exercise streaks (current + all-time record), a calories-eaten chart, a calories-burnt chart, and a weight chart (actual vs. a projected trendline calculated from your logged calories and a Mifflin-St Jeor maintenance-calorie estimate).
- **Dark mode**, with a toggle that remembers your choice.
- **Export / import** — download all your data as a JSON file, or restore from one (with a confirmation before it overwrites anything).

## Running it

No build step, no dependencies. Just open `calorie-tracker.html` in a browser, or serve it locally with something like VS Code's "Live Server" extension.

## Hosting it (e.g. GitHub Pages)

Push this file to a repo and enable GitHub Pages, or open it locally — either works. Note: your data lives in the browser (see below), tied to whatever URL you open the app from. If you test it locally (`file://...`) and then also use it at a live URL (`https://...`), those count as two different places to the browser, so your data won't automatically carry over between them — use Export on one and Import on the other to move it across, once.

Ordinary code updates (editing the file and pushing again) are safe and won't touch your data, as long as you keep opening the app from the same URL.

## How data is stored

Everything is saved in the browser's `localStorage` — there's no server and nothing is sent anywhere. That means:
- Your data persists across sessions as long as you keep using the same browser on the same device without clearing its site data.
- It does **not** sync across devices or browsers on its own.
- Use the **Export data** button (History tab) periodically as a backup, and **Import data** to restore it (on the same device, a new device, or after clearing browser data).

## Tech

Plain HTML, CSS, and vanilla JavaScript in one file. No frameworks, no npm packages, no external requests. Charts are hand-drawn inline SVG.
