# Hint Laundry & Dry Cleaners — staff app

Point-of-sale app for the counter: orders, payments, slips, receipts and
WhatsApp notifications. Runs at https://hint-na.github.io/hint-laundry/ and
installs to a phone's home screen (Add to Home Screen) so it opens instantly,
even with no internet.

## Files

| File | What it is |
|---|---|
| `index.html` | Small page shell: fonts, icons, script tags, service-worker registration |
| `app.jsx` | **The app source — edit this one** (React JSX) |
| `app.js` | Compiled copy of `app.jsx` that the browser actually runs |
| `sw.js` | Service worker — caches everything for offline use |
| `manifest.webmanifest` | Home-screen install details (name, icons, colors) |
| `vendor/` | React and the Excel library, self-hosted |
| `fonts/` | Inter + IBM Plex Mono, self-hosted |
| `icons/` | App icons |

## Making a change

1. Edit `app.jsx`.
2. Compile it:
   ```
   npm install --no-save @babel/cli @babel/core @babel/preset-react
   npx babel --presets @babel/preset-react --no-comments app.jsx -o app.js
   ```
3. Bump `VERSION` in `sw.js` (e.g. `v3.0.0` → `v3.0.1`) so phones fetch the new build.
4. Commit and push — GitHub Pages redeploys automatically.

Data is stored on each device (localStorage) with daily backup downloads for
the owner. Moving to a shared cloud database is planned as Phase 2.
