<div align="center">
  <img src="logo.png" alt="Recurring Expenses Tracker" width="128">
  <h1>Recurring Expenses Tracker</h1>
  <p><em>Track subscriptions. Own your data.</em></p>
</div>

A small, on-device tracker for monthly and annual expenses. Runs as an installable web app on iOS, iPadOS, and desktop browsers. No accounts, no servers, no analytics.

**Live app:** [bcruz22.github.io/expenses-tracker](https://bcruz22.github.io/expenses-tracker/)

## What it does

- Track recurring monthly or annual expenses across categories (Streaming, Software, Utilities, Insurance, Fitness, Subscriptions, Other)
- See total monthly and annual spend at a glance, broken down per category with its own bar, so one large category (e.g. mortgage under Insurance) never crowds out the rest
- Get flagged on expenses coming due in the next 14 days, with free trials floating to the top
- Group items into bundles (e.g. Xfinity bundle covering Disney+ and Hulu). Assign, move, or unbundle any item inline from its row.
- **Bundle savings analysis:** for bundle children, set their standalone cost (what they'd cost outside the bundle). The parent then shows whether the bundle is saving you money or overpaying vs paying for each piece separately.
- Track price changes over time — see a delta indicator when a subscription cost goes up or down
- Search and sort as the list grows
- **Compact mode:** condenses each row's detail (due date, bundle, trial, notes) behind a tap-to-expand toggle, plus tighter spacing throughout. Auto-enables under 640px, or force it on/off from the header.
- Export as CSV, plaintext JSON, or password-encrypted JSON; import any of these back later
- Follows system light/dark preference, with a manual override
- Works offline once installed

## Privacy

All data lives in your device's `localStorage`. Nothing is sent to any server. If you install the app to your home screen on multiple devices, each device keeps its own private copy — there's no sync.

If you share the app link with someone else, they get their own private, empty instance to fill in. Nothing you enter and nothing they enter ever crosses paths.

If you use the **Export encrypted** feature, the backup file uses AES-GCM with a PBKDF2-derived key (250,000 iterations, SHA-256). If you lose the password, the backup cannot be recovered.

## Install on iPhone / iPad

1. Open [the live app](https://bcruz22.github.io/expenses-tracker/) in Safari
2. Tap the Share button
3. Tap **Add to Home Screen**
4. Launch it from the icon on your home screen for the full-screen experience

Add to Home Screen also protects your data from Safari's periodic storage cleanup — bookmarked sites can have their storage cleared after ~7 days of inactivity, but installed sites don't.

## Files

- `index.html` — the entire application (HTML, CSS, JS in one file)
- `sw.js` — service worker for offline support
- `manifest.json` — PWA metadata
- `icon-180.png`, `icon-192.png`, `icon-512.png` — home screen icons
- `logo.png` — app logo (used in this README)
- `social-preview.png` — GitHub social preview card

## Deploying a new version

1. Edit files as needed
2. In `sw.js`, bump `CACHE_NAME` (e.g. `expenses-tracker-v6` → `v7`) so existing installs pick up the new version
3. Commit and push to `main` — GitHub Pages rebuilds automatically
4. Installed devices will show a "New version available" banner on their next visit

## License

MIT — see [LICENSE](LICENSE).

