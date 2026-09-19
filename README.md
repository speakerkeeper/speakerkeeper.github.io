# speakerkeeper.github.io

Marketing site for **[Speaker Keeper](https://github.com/kevinabouhanna/speaker-keeper)**,
a tiny Windows tray app that keeps a Bluetooth speaker from idling off.

Live at **https://speakerkeeper.github.io**

## What's here

```
index.html      the whole page
styles.css      design tokens + layout
assets/         logo (128/256) and favicon, copied from the app repo
```

Static HTML and CSS with one small inline script for the FAQ accordion. No build
step, no dependencies. GitHub Pages serves the files as they are.

## Brand

Colour follows a 60/30/10 split, and the ratio is the point:

| Share | Role | Light | Dark |
|---|---|---|---|
| 60 | Paper: the field everything sits on | `#ffffff` / `#f7f9fc` | `#0b0e14` / `#0f131b` |
| 30 | Ink: type, hairlines, panel fills | `#0b0e14` · `#5a6472` · `#e3e8f0` | `#f1f4f9` · `#98a3b5` · `#1f2734` |
| 10 | Accent: Bluetooth blue | `#0f71fa` | `#4b9bff` |

Blue is reserved for CTAs, the one emphasised phrase in the headline, live states
and small indicators. If it starts appearing in body copy or section fills, the
ratio has slipped and the page stops reading as calm.

The accent matches the app icon's gradient (`#4fa8ff` → `#0b4ed6`), so the tray
icon and the site are recognisably the same product.

Type is [Inter](https://rsms.me/inter/), tight tracking on display sizes.

## Working on it locally

```bash
python -m http.server 8000
```

Then open <http://localhost:8000>. Pushing to `main` publishes.
