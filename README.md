# Disgrace DB — static GitHub Pages edition

This export was made from the supplied `Disgrace-DB (1).html` without changing card IDs, names, stats, or effect descriptions. Embedded artwork was extracted to `assets/cards/` so the browser and Buddyfight Godot application can load cards without downloading a 50 MB HTML page.

## GitHub Pages setup

1. Copy the *contents* of this folder (not the ZIP itself) to the root of your `disgrace-db` GitHub repository.
2. In GitHub, go to **Settings → Pages**, select **Deploy from a branch**, **main**, **/(root)**, and Save.
3. Website: `https://dbarnesirick-arch.github.io/disgrace-db/`
4. Godot card feed: `https://dbarnesirick-arch.github.io/disgrace-db/cards.json`

## Important: publishing is different from browser saving

The current **Create Card** dialog saves new cards only in that browser's `localStorage`. Those cards do not automatically go to GitHub and cannot be read from another computer. This site is **read-only shared publishing** until a separate secure publishing system is built.

To publish a newly created/edited card for everyone, update and redeploy `cards.json` and `cards-data.js` (and any needed artwork), or later use a secure publish backend. Do not put GitHub passwords or tokens in `index.html` or JavaScript.

## Data format / migration

- `cards.json` is a JSON **array**. Card `id` values are intentionally preserved as strings; do not re-number.
- `type` remains numeric (1 Monster, 2 Item, 3 Spell, 4 Impact, 5 Flag, 6 Impact Monster).
- Image fields are relative paths like `assets/cards/0001_...jpg`, resolved relative to the hosted site. Godot needs a remote artwork downloader/cache to show those images; Godot's `load("http...")` cannot read HTTP URLs.
- `cards-data.js` supplies the same catalog to the existing website, so the website still runs locally as a file. `cards.json` is the public HTTP feed used by the game.
- Local edits/decks in Godot should not be overwritten automatically by a fetched snapshot. Implement synchronization as an ID-based overlay with offline cache and clear precedence rules.
- Public GitHub Pages exposes all published card data and images to visitors. Confirm you have permission to publish the artwork.

No live publishing or GitHub push is included in this export.
