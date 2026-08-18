# Gledé Browne Kabongo — Website Prototype

Static, high-fidelity UI prototypes for the redesign of
[gledekabongo.com](https://www.gledekabongo.com/), built for client approval and
intended for later conversion to WordPress.

## Pages

| File | Page | Notes |
|---|---|---|
| `index.html` | Homepage | Hero, featured books, awards band, newsletter, series, speaking, closing statement |
| `books.html` | Books | Full catalogue — standalones, Fearless, Miami Elite, Malicious Games, novellas, audiobooks |
| `about.html` | About | Biography, themes, craft, on writing, readers, personal closing |
| `speaker.html` | Speaker Profile | Positioning, credentials, speaking areas, audiences, engagements, recognition |

Open any file directly in a browser — no build step, no server, no dependencies.

## What these are

Visual prototypes only. There is deliberately **no** backend, CMS, database, API,
cart, checkout, authentication or form processing. Specifically:

- No `<form>` element exists on any page. The newsletter field on the homepage is a
  styled read-only input; its button is a `<span>`.
- The only JavaScript is a ~10-line mobile menu toggle, repeated per page.
- Buttons and links use real destinations where they exist, placeholders elsewhere.

## Design system

Each page carries its own inline `<style>` block so it can be previewed in isolation,
but all four share one system. The tokens are identical everywhere:

```css
--navy: #05347E;   /* brand — navigation, dark sections, footer */
--blue: #3E7FE6;   /* brand — links, section labels, accents    */
--gold: #FFDB4F;   /* brand — used sparingly for emphasis       */
```

Plus derived neutrals (`--navy-deep`, `--navy-ink`, `--paper`, `--paper-warm`,
`--blue-wash`, `--ink`, `--ink-soft`, `--ink-mute`) and shared rhythm tokens
(`--shell`, `--gutter`, `--section`).

Type: **Cormorant Garamond** for display and editorial statements, **Inter** for UI,
body copy and eyebrows. Loaded from Google Fonts.

Shared component classes across all pages: `.shell`, `.section`, `.eyebrow`,
`.display`, `.h2`, `.h3`, `.lede`, `.body`, `.meta`, `.btn`, `.link-arrow`,
`.site-header`, `.nav`, `.submenu`, `.mobile-nav`, `.site-footer`.

When converting to WordPress, the `<style>` blocks should be consolidated into a
single stylesheet — they are near-identical up to each page's own section rules.

## Imagery

Every image is a real asset from the client's existing site, served from their own
CDN (`static.wixstatic.com`). No AI-generated imagery, no stock photography.

Several images use Wix crop parameters in the URL to normalise them — most notably
the book covers on `books.html`, which are cropped to their alpha bounding boxes so
all fifteen sit in one consistent 71:100 frame despite coming from three different
3D-render templates.

Because images load from an external CDN, the pages need an internet connection to
render fully.

## Content

All copy is taken from the live site — book descriptions, series copy, biography,
awards, speaking engagements, newsletter messaging. Nothing was fabricated. Where the
source was unavailable, the page says less rather than inventing.

## Responsive

Verified in headless Chrome at 375, 390, 430, 768, 1024 and 1440 px. No horizontal
overflow at any width. Mobile layouts are re-composed rather than scaled — the About
hero, for example, leads with a full-bleed portrait on mobile and the type block
second, which is the reverse of its desktop arrangement.

## Open items for the client

- **Truncated sentence on the live bio.** `/bio` ends mid-word: *"Gledé Browne Kabongo
  writes addictive psychological thrillers a"*. Left out rather than guessed.
- **Fearless series numbering** on `books.html` runs Reign → Winds → Autumn → Game as
  requested, which is the reverse of publication order. Worth confirming.
- **Low-resolution assets.** The book-signing photograph used on `about.html` is only
  300×221 px natively. A higher-resolution original would support a much larger crop.
- **No stage photography.** The speaker page uses the one candid lectern shot that
  exists. A photo of Gledé on stage with an audience visible would be the single
  highest-value asset to add.
- **Speaker inquiry flow** currently points at a Google Form, matching the live site.
  Worth designing a proper inquiry page during the WordPress build.
- **Covers not yet available** for *A Mind of Malice* and *A Legacy of Malice*; both
  use a designed "cover reveal to come" placard rather than a fabricated jacket.
