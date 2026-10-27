# Gianna’s Travel Companion — V1.1 Full Bangkok Content

Static, offline-first iPhone PWA for Bangkok 28 Oct – 2 Nov 2026.

## What's included

- Seven original modules: Daily Timeline, Offline Checklist, Place Cards, Airport Survival, Budget Tracker, Travel Phrasebook, Emergency Kit.
- **Full Notes**: all six original text files copied verbatim, including long explanations, tables, links, checklists, maps, transport details and phrases. Search within a day, jump by headings, copy or download original text.
- `content/index.json`: source file metadata, heading index, line counts and SHA-256 integrity hashes.
- Original source texts in `content/day-01.txt` through `content/day-06.txt`.

## Publish free on GitHub Pages

1. Create a **public** GitHub repository. Upload **the contents of this ZIP**, preserving paths, to the repository root.
2. GitHub repository → Settings → Pages → Deploy from branch → `main` / `/(root)` → Save.
3. Wait for the HTTPS Pages URL. Open it in Safari on iPhone, then Share → Add to Home Screen.
4. Open once while online, then test Airplane Mode. The service worker precaches the six complete text files, JSON, app assets and icons.

## Local test

From this folder run `python3 -m http.server 8000` and open `http://localhost:8000/` in a browser. `file://` is not sufficient for service worker and fetch.

## Data safety and limitations

- All six source files are bundled in this repository. **Do not add passport photos, booking codes, personal phone numbers, banking data, or other secrets to a public repository.** Review original texts before uploading.
- Checklist and expenses persist in localStorage on the same browser/device. They are not synced to Notion and can be lost if browser data is cleared. Export budget CSV regularly.
- Source text is preserved as text (not formatted Markdown), intentionally avoiding third-party libraries or external CDNs. URLs in the full notes are shown as text; use Place Cards for map links.
- `data.json` contains the earlier structured, abridged summaries. **Full Notes** contains the complete six source files; it does not automatically convert every original checklist item into an interactive checkbox.
- Prices, flight times, entry rules and operating hours in the original notes are historical/planned, not real-time verified. Confirm against current tickets and official providers.
- No external fonts, scripts, analytics or payment features.

## Updating

Edit the original source under `content/`, regenerate the heading index and hashes, and change the cache version in `sw.js`. Test offline before deployment. Existing local checklist/expenses are retained because the storage prefix remains `gianna-v1-`.
