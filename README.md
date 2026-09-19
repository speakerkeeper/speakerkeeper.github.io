# speakerkeeper.github.io

Marketing site for **[Speaker Keeper](https://github.com/kevinabouhanna/speaker-keeper)**,
a tiny Windows tray app that keeps a Bluetooth speaker from idling off.

Live at **https://speakerkeeper.github.io**

## What's here

```
index.html      the whole page
styles.css      design tokens + layout
llms.txt        plain-text brief for assistants and answer engines
robots.txt      crawler directives, points at the sitemap
sitemap.xml     the one URL, with its lastmod
CLAUDE.md       conventions for anyone (or anything) editing this
assets/         logo (128/256), favicon, and the link-preview card
```

`assets/og.png` is what unfurls when the site is linked: the icon, the name, and
five words saying what it does. It is a screenshot of `assets/og-card.html`, and
that file carries the command that regenerates it.

Static HTML and CSS with one small inline script for the carousel, the full-size
viewer and the FAQ accordion. No build step, no dependencies. GitHub Pages serves
the files as they are.

`<head>` carries two JSON-LD blocks: a `SoftwareApplication` describing the app and
a `FAQPage` generated from the visible FAQ. The second has to match the questions
on the page word for word, so regenerate it rather than editing it by hand.

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

Three semantic hues sit alongside the blue, each as a trio: the hue itself, a
`-tint` for pastel fills and an `-ink` dark enough to read on that fill.

| Token | Where it is used | Light | Dark |
|---|---|---|---|
| `--red` | The problem section: its eyebrow and card numbers | `#d93a3a` | `#ff7a7a` |
| `--green` | What changes: its eyebrow and step rules, and the hero's ticks | `#2ea043` | `#56d364` |
| `--yellow` | The SmartScreen caution | `#e0a200` | `#e3b341` |

Those two sections re-point `--accent` on themselves, so everything inside them
follows without a second set of rules.

Type is [Inter](https://rsms.me/inter/), tight tracking on display sizes.

## Working on it locally

```bash
python -m http.server 8000
```

Then open <http://localhost:8000>. Pushing to `main` publishes.
