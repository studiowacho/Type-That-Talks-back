---
name: type-that-talks-back
description: Michal Vasko's font pairing and text-entrance system for product UI, from typethattalksback (Duet). Use this skill whenever the user asks about font pairings, choosing a headline or body typeface, typography systems, type tokens, display vs body fonts, or wants text entrance animations (rise, blur-in, pop, clip reveal, tracking) for headlines and paragraphs. Also trigger when the user says "use my pairings skill", mentions "type that talks back", asks to "make this type animate in", wants typography that doesn't look default, or is building any landing page, hero, card grid, or marketing surface where type hierarchy matters — even if they don't say "font pairing" explicitly.
---

# Type That Talks Back

Eight font pairings for product UI, each built on a named principle, plus five
text entrance animations — all as copy-paste CSS with zero dependencies. Fonts
load from Google Fonts unless noted. This skill encodes the system from
typethattalksback by Michal Vasko.

## How to use this skill

1. **Picking type for a project** → choose a pairing by principle (see table),
   apply its CSS tokens verbatim.
2. **Animating text in** → pick an entrance, bake the parameters, add the
   splitter script. Never animate without the reduced-motion fallback.
3. **Auditing existing type** → use the `pairings review` command behavior.

## The principles (pick by intent)

| Pairing | Principle | Reach for it when |
|---|---|---|
| Fraunces + Inter | Style contrast | Editorial voice over neutral UI |
| Space Grotesk + IBM Plex Sans | Shared geometry | Dashboards; numbers with personality |
| Playfair Display + Source Sans 3 | Contrast of contrast | Big statements, quiet support |
| DM Serif Display + DM Sans | Superfamily | Zero-risk harmony, designed together |
| Archivo Black + Archivo | Weight contrast | One family, hierarchy from weight alone |
| Inter + JetBrains Mono | Division of labor | Sans for prose, mono for data |
| Work Sans + Lora | Role inversion | Long-form reading; serif body, sans UI |
| Libre Franklin + Libre Caslon Text | Historical kinship | News/editorial; shared era, shared mood |

## The token contract

Every pairing resolves to the same three roles. Swap families, keep the system.

```css
:root {
  --font-display: /* the voice */;
  --font-body:    /* the reading */;
  --font-mono:    "JetBrains Mono", ui-monospace, monospace;

  --text-xs: 0.75rem;  --text-sm: 0.875rem;  --text-md: 1rem;
  --text-xl: 1.25rem;  --text-2xl: 1.75rem;  --text-3xl: 2.5rem;

  --leading-display: 1.15;
  --leading-body: 1.6;
}
```

## The pairings (copy-paste CSS)

### 1 · Fraunces + Inter — Style contrast
```css
@import url('https://fonts.googleapis.com/css2?family=Fraunces:opsz,wght@9..144,400;9..144,600&family=Inter:wght@400;500;600&display=swap');
:root { --font-display: "Fraunces", Georgia, serif; --font-body: "Inter", system-ui, sans-serif; }
.display { font-family: var(--font-display); font-weight: 600; line-height: 1.2; letter-spacing: -0.015em; }
.body    { font-family: var(--font-body); font-weight: 400; line-height: 1.65; }
```

### 2 · Space Grotesk + IBM Plex Sans — Shared geometry
```css
@import url('https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@500;700&family=IBM+Plex+Sans:wght@400;500&display=swap');
:root { --font-display: "Space Grotesk", system-ui, sans-serif; --font-body: "IBM Plex Sans", system-ui, sans-serif; }
.display { font-family: var(--font-display); font-weight: 700; line-height: 1.1; letter-spacing: -0.02em; }
.body    { font-family: var(--font-body); font-weight: 400; line-height: 1.6; }
```

### 3 · Playfair Display + Source Sans 3 — Contrast of contrast
```css
@import url('https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,500;1,500&family=Source+Sans+3:wght@400;600&display=swap');
:root { --font-display: "Playfair Display", Georgia, serif; --font-body: "Source Sans 3", system-ui, sans-serif; }
.display { font-family: var(--font-display); font-weight: 500; line-height: 1.4; }
.body    { font-family: var(--font-body); font-weight: 400; line-height: 1.6; }
```

### 4 · DM Serif Display + DM Sans — Superfamily
```css
@import url('https://fonts.googleapis.com/css2?family=DM+Serif+Display&family=DM+Sans:wght@400;500&display=swap');
:root { --font-display: "DM Serif Display", Georgia, serif; --font-body: "DM Sans", system-ui, sans-serif; }
.display { font-family: var(--font-display); font-weight: 400; line-height: 1.1; }
.body    { font-family: var(--font-body); font-weight: 400; line-height: 1.6; }
```

### 5 · Archivo Black + Archivo — Weight contrast
```css
@import url('https://fonts.googleapis.com/css2?family=Archivo:wght@400;500;900&display=swap');
:root { --font-display: "Archivo", system-ui, sans-serif; --font-body: "Archivo", system-ui, sans-serif; }
.display { font-family: var(--font-display); font-weight: 900; line-height: 1.05; letter-spacing: -0.02em; text-transform: uppercase; }
.body    { font-family: var(--font-body); font-weight: 400; line-height: 1.6; }
```

### 6 · Inter + JetBrains Mono — Division of labor
```css
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600&family=JetBrains+Mono:wght@400;500&display=swap');
:root { --font-body: "Inter", system-ui, sans-serif; --font-mono: "JetBrains Mono", ui-monospace, monospace; }
.body { font-family: var(--font-body); font-weight: 400; line-height: 1.6; }
.data { font-family: var(--font-mono); font-weight: 500; font-variant-numeric: tabular-nums; }
```

### 7 · Work Sans + Lora — Role inversion (serif body)
```css
@import url('https://fonts.googleapis.com/css2?family=Work+Sans:wght@400;600&family=Lora:ital,wght@0,400;1,400&display=swap');
:root { --font-display: "Work Sans", system-ui, sans-serif; --font-body: "Lora", Georgia, serif; }
.display { font-family: var(--font-display); font-weight: 600; line-height: 1.25; letter-spacing: -0.01em; }
.body    { font-family: var(--font-body); font-weight: 400; font-size: 1.0625rem; line-height: 1.75; }
```

### 8 · Libre Franklin + Libre Caslon Text — Historical kinship
```css
@import url('https://fonts.googleapis.com/css2?family=Libre+Franklin:wght@500;700;900&family=Libre+Caslon+Text&display=swap');
:root { --font-display: "Libre Franklin", system-ui, sans-serif; --font-body: "Libre Caslon Text", Georgia, serif; }
.display { font-family: var(--font-display); font-weight: 900; line-height: 1.15; letter-spacing: -0.015em; }
.body    { font-family: var(--font-body); font-weight: 400; line-height: 1.6; }
```

Bonus display face: **Nyght Serif** (SIL OFL, Maksym Kobuzan) — a spicy
high-contrast serif for hero moments. Not on Google Fonts; self-host it.

## Text entrances

Five entrance animations for headlines and paragraphs. Apply class
`duet-animate` to any text element, include one keyframe block, and add the
splitter. Defaults that feel right: **620ms duration, 39ms word stagger,
cubic-bezier(0.22, 1, 0.36, 1)** easing, 6px blur.

Base unit CSS (all entrances share this):

```css
.duet-u {
  display: inline-block; opacity: 0; /* clip reveal: opacity 1 */
  animation: duetEntrance {DUR}ms cubic-bezier(0.22, 1, 0.36, 1) forwards;
  animation-delay: calc(var(--i) * {STAGGER}ms);
}
@media (prefers-reduced-motion: reduce) {
  .duet-u { animation: none; opacity: 1; clip-path: none; }
}
```

Keyframes per entrance — pick one as `duetEntrance`:

```css
/* Rise & blur — the default; safe everywhere */
from { opacity: 0; transform: translateY(0.65em); filter: blur(6px); }
to   { opacity: 1; transform: none; filter: blur(0); }

/* Blur in — soft focus pull */
from { opacity: 0; filter: blur(6px); transform: scale(1.03); }
to   { opacity: 1; filter: blur(0); transform: none; }

/* Scale pop — playful */
from { opacity: 0; transform: scale(0.6); filter: blur(3px); }
to   { opacity: 1; transform: scale(1); filter: blur(0); }

/* Clip reveal — editorial; .duet-u starts at opacity: 1 */
from { opacity: 1; clip-path: inset(0 0 100% 0); transform: translateY(0.35em); }
to   { opacity: 1; clip-path: inset(-0.25em -0.15em -0.25em -0.15em); transform: none; }

/* Tracking in — cinematic titles */
from { opacity: 0; letter-spacing: 0.35em; filter: blur(3px); }
to   { opacity: 1; letter-spacing: normal; filter: blur(0); }
```

Splitter — words (default):

```html
<script>
document.querySelectorAll('.duet-animate').forEach(el => {
  el.innerHTML = el.textContent.trim().split(/\s+/)
    .map((w, i) => '<span class="duet-u" style="--i:' + i + '">' + w + '</span>')
    .join(' ');
});
</script>
```

Splitter — letters (divide the stagger by 3 to keep total time sane):

```html
<script>
document.querySelectorAll('.duet-animate').forEach(el => {
  let i = 0;
  el.innerHTML = el.textContent.trim().split(/\s+/).map(w =>
    '<span style="white-space:nowrap">' + Array.from(w).map(ch =>
      '<span class="duet-u" style="--i:' + (i++) + '">' + ch + '</span>'
    ).join('') + '</span>'
  ).join(' ');
});
</script>
```

## Commands

`pairings reveal` — List all eight pairings with their principles as a
numbered text list. Also triggers on "list the pairings" or "what pairings
are available".

`pairings review` — Scan the project for font-family declarations, count
distinct families, flag pages using more than two non-mono families, missing
fallback stacks, hardcoded sizes outside the token scale, and entrances
without reduced-motion fallbacks. Read-only; output a per-file report. Also
triggers on "audit my typography" or "review my fonts".

`pairings apply` — Infer the surface type from context (dashboard, editorial,
marketing, reading, news), propose the best-fit pairing with a one-line
rationale, then install its CSS after the user confirms. Name a pairing
directly to skip inference — e.g. `pairings apply fraunces-inter`. Also
triggers on "pick fonts for this" or "add the right pairing here".

## Rules

- Two families maximum per surface (mono for data doesn't count).
- The display face earns its place at large sizes only; never set body copy
  in a display face.
- Use the token contract — swap `--font-display` / `--font-body`, never
  hardcode families on components.
- Headlines tight (1.05–1.25 leading, slight negative tracking); body loose
  (1.6–1.75, neutral tracking).
- Every entrance ships with the `prefers-reduced-motion` fallback. No
  exceptions.
- Letters mode: stagger ÷ 3. Words mode: 30–50ms stagger reads best.
- When in doubt: Fraunces + Inter with Rise & blur at the defaults.
