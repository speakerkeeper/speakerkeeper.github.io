# Working on this site

Static HTML and CSS with one inline script. No build step, no dependencies.
`index.html` is the whole page, `styles.css` holds the tokens and the layout.
Preview with `python -m http.server 8000`; pushing to `main` publishes.

## Writing

- **Never use em dashes (—) or en dashes (–) in prose.** Not in copy, not in
  comments, not in commit messages. Use a comma, a colon, or two sentences.
- **Never write "speaker" on its own when the device is meant. Write "Bluetooth
  speaker".** The product only works on Bluetooth speakers, and a reader
  skimming should never have to infer which kind. "Speaker Keeper" is the
  product name and stays as it is.
- Say what a thing does, in the words someone would use to search for it.
  Short sentences. No marketing adjectives that carry no information.

## Design

- Colour follows 60/30/10: paper, ink, and one accent. The accent is Bluetooth
  blue and belongs to CTAs, live states and a single headline phrase. Two
  sections re-point the accent variables on themselves: `#problem` runs red and
  `#how` runs green, so the problem and the fix are told apart at a glance.
  Semantic colours (`--red`, `--green`, `--yellow`) each have a `-tint` for
  pastel fills and an `-ink` for readable type on that fill.
- Every colour is a token on `:root`, redefined under
  `@media (prefers-color-scheme: dark)` guarded by `:root:not([data-theme="light"])`
  and again under `:root[data-theme="dark"]`. Adding a raw hex to a rule is a bug.
- A primary and a secondary button sitting together are the same width: the pair
  is a grid whose track is sized by the wider label, side by side on desktop and
  stacked on phones. Button labels never wrap.
- Everything has to work at 320px wide with no horizontal page scroll.

## Findability

The page is the product's front door for people searching for the problem, so
keep these in step whenever the copy changes:

- The `FAQPage` JSON-LD in `<head>` is generated from the visible FAQ text and
  must match it exactly. Regenerate it rather than hand-editing.
- `llms.txt` is the plain-text brief for assistants and answer engines. Update it
  when a fact about the product changes.
- `sitemap.xml` carries a `lastmod`. Bump it on a real content change.
- `assets/og.png` is the link preview. It is rendered from `assets/og-card.html`
  at 1200x630, and the command to redo it is in that file. Change one and change
  the other.

## Do not mention

- The media keys. Speaker Keeper publishes no media transport session, so play,
  pause and skip are unaffected, but that is not something the site talks about
  in any form.
