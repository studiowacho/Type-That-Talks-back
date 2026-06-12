# Type That Talks Back — Font pairings for product UI

Made by Michal Vasko • Made in San Francisco ❤️

A collection of essential font pairings for product UI that you can copy and paste into any project. Every pairing names the **principle** that makes it work, and an **Inspect** mode overlays redline spec annotations (family · weight · size/leading · tracking) on every specimen — like flipping on redlines in a design review.

## Motion studio

Every specimen's text can animate in. The motion bar above the grid controls:

- **Entrance** — Rise & blur, Blur in, Scale pop, Clip reveal, Tracking in
- **Split by** — animate per word or per letter (letter stagger auto-scales to stay snappy)
- **Duration, Stagger, Easing, Blur** — live sliders; every change replays the grid

Hover any card and hit **↻ Animate** to replay just that specimen. `prefers-reduced-motion` is respected everywhere.

**Copy code** on each card exports a single paste-ready snippet — Google Fonts import, the pairing's type tokens, the entrance animation with your exact settings baked in, and a 6-line splitter script. Add `class="duet-animate"` to any text element on your site and it just works.

## The pairings

| Pairing | Principle |
|---|---|
| Fraunces + Inter | Style contrast |
| Space Grotesk + IBM Plex Sans | Shared geometry |
| Playfair Display + Source Sans 3 | Contrast of contrast |
| DM Serif Display + DM Sans | Superfamily |
| Archivo Black + Archivo | Weight contrast |
| Inter + JetBrains Mono | Division of labor |
| Work Sans + Lora | Role inversion |
| Libre Franklin + Libre Caslon Text | Historical kinship |

## The skill

This whole system ships as an AI skill — `SKILL.md` at the repo root teaches a coding agent (Claude Code, Cursor, Copilot, etc.) all eight pairings, the token contract, and the five entrances, plus `pairings reveal / review / apply` commands.

```
npx skills add <your-github-username>/<repo-name>
```

## Stack

None. One HTML file, zero dependencies, zero build step. Fonts load from Google Fonts. Light/dark theme follows your system preference.

## Run it

Open `index.html` in a browser. That's it.

## Deploy to GitHub Pages

1. Push this repo to GitHub
2. Settings → Pages → Source: **Deploy from a branch** → `main` / root
3. Live at `https://<your-username>.github.io/duet/`

## Add a pairing

1. Add a `<article class="card">` block in `index.html` with a new specimen
2. Add `data-spec="Family · weight · size/leading"` attributes for Inspect mode
3. Add a matching CSS snippet to the `snippets` object at the bottom of the file
4. Add the family to the Google Fonts `<link>` in `<head>`

## The remix layer

Tap any pairing to open it full-size. The modal is a playground: the headline and paragraph are **editable — type your own copy** and see it set in the pairing instantly. Remix the display and body fonts across the whole library, scale the title, flip between four canvases (deep, silver, phosphor, paper), replay the entrance with your current motion settings, and copy code that matches exactly what you built.

The hero is set in **Nyght Serif** by Maksym Kobuzan (SIL Open Font License), base64-embedded so the site stays a single file — and its letters lift when you hover them. The title talks back.

## Design language

Dark-first bento grid with one ember-orange accent. All site chrome is set in JetBrains Mono — the specimens are the only humanist type on the page, which is the point. Cards sit at a 26px radius, lift and glow on hover, and hovering any specimen replays its text entrance. Light mode swaps the charcoal canvas for warm cream. A static dotted grid and a whisper of film grain sit behind everything — pure CSS, zero JavaScript, completely still. Everything settles instantly under `prefers-reduced-motion`.
