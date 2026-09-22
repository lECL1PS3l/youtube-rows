# YouTube Rows

Browser extension (Brave / Chromium, Manifest V3) that shows **6 videos per row** on YouTube instead of the default 3.

## Install

1. Clone this repo.
2. Open `brave://extensions` (or `chrome://extensions`).
3. Enable **Developer mode**.
4. Click **Load unpacked** and select the folder.
5. Open youtube.com — the grid now fits 6 thumbnails per row.

Toggle on/off via the extension's toolbar icon.

## Preview

| Before (3 per row) | After (6 per row) |
| --- | --- |
| ![](docs/before.png) | ![](docs/after.png) |

## How it works

YouTube sizes grid items with `width: calc(100%/var(--ytd-rich-grid-items-per-row) - var(--ytd-rich-grid-item-margin))`. The extension just overrides that CSS variable to `6`, so the native layout math does the rest — no DOM rewriting, no perf cost.

## Files

| File | Purpose |
| --- | --- |
| `manifest.json` | MV3 manifest |
| `content.js` | Adds/removes the `yt-rows-6` class, listens for toggle changes |
| `content.css` | The CSS variable override |
| `popup.html` / `popup.js` | On/off switch, persisted in `chrome.storage.local` |
