# YouTube Rows

Browser extension (Brave / Chromium, Manifest V3) that shows **6 videos per row** on YouTube instead of the default 3.

## Preview

| Before (3 per row) | After (6 per row) |
| --- | --- |
| ![](screens/before.png) | ![](screens/after.png) |

## Install from a ZIP (no cloning needed)

1. Download `youtube-rows-v1.0.0.zip` from [Releases](../../releases/latest).
2. **Extract** the ZIP anywhere, e.g. to your Desktop.
3. Open `brave://extensions` (Brave), `chrome://extensions` (Chrome, Chromium, Edge, Vivaldi, Opera).
4. Turn on **Developer mode** (top-right toggle).
5. Click **Load unpacked**, then select the extracted `YouTube Rows` folder.
6. Open [youtube.com](https://www.youtube.com/) — you should now see 6 thumbnails per row.

Turn it on/off with the extension's toolbar icon.

## Install for developers

```bash
git clone https://github.com/lECL1PS3l/youtube-rows.git
```

Then steps 3–6 above, pointing at the cloned folder.

## How it works

YouTube sizes grid items with `width: calc(100%/var(--ytd-rich-grid-items-per-row) - var(--ytd-rich-grid-item-margin))`. The extension overrides that CSS variable to `6`, so the native layout math does the rest — no DOM rewriting, no perf cost.

## Files

| File | Purpose |
| --- | --- |
| `manifest.json` | MV3 manifest |
| `content.js` | Adds/removes the `yt-rows-6` class, listens for toggle changes |
| `content.css` | The CSS variable override |
| `popup.html` / `popup.js` | On/off switch, persisted in `chrome.storage.local` |

## License

MIT — see [LICENSE](LICENSE).
