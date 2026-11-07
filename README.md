# RockHound AI — PWA v0.1

A mobile-first, offline-capable rock collection app with photo upload, local IndexedDB storage, edit/delete, search, JSON photo backups, and a field guide.

## Install on Android

1. Host the contents of this directory on **HTTPS** (GitHub Pages, Netlify, or Cloudflare Pages all work). The ZIP itself is not an installable APK; opening index.html as a local file does not provide full PWA functionality.
2. Open the HTTPS site in Chrome on Android.
3. Chrome menu → **Add to Home screen** or **Install app** (wording varies).
4. Open the installed app and add a specimen. Reopen it offline to test cached app access.

## Quick local development

Run `python3 -m http.server 8000` inside this folder, then open `http://localhost:8000` on the same computer. For testing on a phone, use HTTPS hosting rather than a LAN HTTP address.

## Storage/privacy

Records and compressed photos live in IndexedDB for the origin on this device. Clearing site data or uninstalling can remove them. Use the full JSON export to back up; JSON imports merge by specimen ID. No data is sent to an AI provider or backend in this version. Browsers may evict storage; offline access requires a successful initial online load.

## AI identification next

Build a backend endpoint (e.g. a serverless function) that accepts an image only with explicit user consent, removes EXIF location metadata, calls a vision-capable model using a server-side API key, and returns structured candidates: rock type, visual evidence, uncertainty, alternative hypotheses, suggested hardness/UV tests. Avoid presenting numeric confidence scores as calibrated without evaluation. Confirm identification before saving. Add rate limiting, authentication if needed, image retention policy, and evaluation with verified samples.

## Other next steps

GPS permission and maps, UV before/after comparison, specimen tagging, encrypted cloud sync (optional), export formats, accessibility and automated mobile tests.
