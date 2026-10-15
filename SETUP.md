# Mental Game mobile app

The app is live at **https://iamjayparmar.github.io/mental-game-mobile/**. Open the link on your phone and use the browser menu to choose **Add to Home Screen** or **Install app**.

## Sign in

Enter your email in the app. Supabase will send a one-time sign-in link; open it on the same device/browser to return to the app. Supabase's default email delivery is enabled. For reliable delivery to more users, configure a custom SMTP provider in Supabase.

## Data privacy

Journal entries are stored in the Supabase project **Trading Psychology Tracker**. The `journal_entries` table has row-level security enabled: signed-in users can read and insert only rows with their own user ID. The app contains only the browser-safe publishable key; it does not contain the database password or a service-role/secret key. The allowed email redirect URL is configured for the hosted app.

The GitHub Pages source repository is public, so the app code is visible. Journal entries remain in Supabase and are protected by authentication and row-level security.

## Project files

- `index.html` — responsive game, journal, sign-in screen, and Supabase integration.
- `app-config.js` — Supabase project URL and browser-safe publishable key.
- `schema.sql` — idempotent SQL used to create the journal table, policies, and index.
- `manifest.webmanifest`, `icon.svg`, `sw.js` — installable app metadata, icon, and cached app shell.
