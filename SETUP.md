# Mental Game mobile app

The Supabase backend is connected to the existing **Trading Psychology Tracker** project. The `journal_entries` table is in place with row-level security enabled and two policies: signed-in users can read and insert only their own entries. The browser app uses the project's public publishable key; no secret key is included in the app.

## One remaining step: host the app

The app must be served from an HTTPS website before email sign-in and Add to Home Screen will work on a phone. Opening `index.html` as a local file is only a preview; browsers block service workers and secure auth redirects from `file://` URLs.

1. Upload the contents of this folder to a static HTTPS host (for example GitHub Pages, Netlify, or Cloudflare Pages).
2. In Supabase Dashboard → **Authentication → URL Configuration**, set **Site URL** to the deployed HTTPS address and add that same address under **Redirect URLs**.
3. Open the deployed address on your phone, enter your email, and use the emailed sign-in link. Choose **Add to Home Screen** / **Install app** in the browser menu.

Supabase email authentication is already enabled. Configure a custom SMTP provider in Supabase before wider use if you need reliable production email delivery.

## Files

- `index.html` — responsive game, journal, sign-in screen, and Supabase integration.
- `app-config.js` — project URL and browser-safe publishable key.
- `schema.sql` — idempotent SQL used to create the journal table, policies, and index.
- `manifest.webmanifest`, `icon.svg`, `sw.js` — installable app metadata, icon, and cached app shell.
