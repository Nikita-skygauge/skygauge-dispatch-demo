# Skygauge Dispatch — public demo

A self-contained sandbox of Skygauge Dispatch on a sample industrial site in Thorold, ON.
Every visitor gets the same sample jobs, notes and email threads; nothing is saved to a server,
and a reload resets everything. No sign-in, no Firebase.

Separate from the production app: no shared data, no shared database.

## Files

- `index.html` — the app (built from the production source with the demo seed data).
- `config.js` — the Google Maps key for the 3D view. Edit this file on GitHub and paste the key between the quotes.

## Maps key

The key is visible to anyone who opens the page, so in Google Cloud Console restrict it to
**Websites: `https://nikita-skygauge.github.io/skygauge-dispatch-demo/*`** (plus any existing sites it serves)
and to the Maps JavaScript / Map Tiles APIs, and set a daily quota cap.

## Base file (what every visitor starts from)

- `seed.json` holds the demo's jobs, notes, email and assets. Visitors load it into memory; a reload resets it.
- To edit it: open the demo with `?author=1` on the end of the URL. The bar at the bottom says you are editing the base file; changes are kept in that browser across reloads. **Download base file** exports it; replace `seed.json` in this repo with it. **Start over** discards that browser's edits.
- Dates are stored with the time the file was saved and shift forward on load, so "2 days ago" and upcoming deadlines stay current.
- The Maps key is never stored in `seed.json`; it comes from `config.js`.
