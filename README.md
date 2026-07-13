# Fancy Font Generator 𝔽𝖆𝖓𝖈𝕪 𝔽𝖔𝖓𝕥 𝕲𝖊𝖓𝖊𝖗𝕒𝕥𝖔𝖗 ☠

A single-file, gothic-punk Unicode text stylizer. Type text once, get it back in 100+ fancy/cursed/chaotic fonts — no fonts actually installed, just clever Unicode character substitution that works anywhere (Discord, Instagram bios, usernames, anywhere text goes).

**Live site:** https://ad0rkableg33k.github.io/FontGenerator.html

---

## Features

- **104 styles** and counting — from clean serif/script/gothic Unicode fonts, to bubble and kawaii styles, combining-diacritic effects (strikethrough, underline, overline), 1337-speak, and full-on chaos mashups that randomly blend two styles together per character.
- **Signature style: BatStyle** — a custom hand-picked glyph mapping (mixed Cyrillic, Greek, and IPA characters) that's the site's flagship look, pinned as the very first style in the list.
- **Live search/filter** — type in the filter box to instantly narrow down the style list by name.
- **Decorator toolbar** — wrap your output in themed bookends (☠ skulls, ⛧ pentagram, ☆ star, 🕸 spider web, 🦇 bat, ⚰️ coffin, 🖤 black heart) with one click.
- **Copy-on-click cards** — click any style's output card to instantly copy that version to your clipboard, with a toast confirmation.
- **Clear button** to reset the input instantly.
- **Gothic-punk visual design** — hot pink and magenta on black, drippy top border, skull-and-pentagram accents, all consistent with the rest of the Unsolicited Deck Pics universe.
- **Sticky nav bar** linking to Unsolicited Deck Pics (tarot/oracle site), Reality is Buffering (webcomic), GitHub, and YouTube.

## How It Works

- A `normal` array holds the 62 standard characters (`A–Z`, `a–z`, `0–9`) in a fixed order.
- Every style is either:
  - A **static 62-item array** of replacement characters in that same order (simple lookup by index), or
  - A **function** `(input) => string` for styles that need logic — random mashups between two other styles, 1337-speak substitution tables, decorative effects like strikethrough/underline, etc.
- Mashup/combo styles reference other styles by their exact key name (e.g. `styles["9. Gothic"]`), so styles can be freely reordered in the file without breaking anything — the lookups happen at render time, not at declaration time.
- The visible order of styles in the UI matches the order they're declared in the `styles` object (JavaScript preserves insertion order for string keys), **not** the numeric prefix in the name — the numbers are just a naming/sorting convenience for humans, not a mechanism the code reads.

## Adding a New Style

1. Pick a unique 62-character mapping (or write a function) covering `A–Z`, `a–z`, `0–9` in that exact order.
2. Add it to the `styles` object wherever you want it to appear in the list — position in the file **is** position in the UI.
3. If it's a static style, double check the array has exactly 62 entries — a short array will silently produce garbled/missing output for the tail-end characters.

## Tech Notes

- Single-file HTML/CSS/JS, no build step, no dependencies — hosted directly on GitHub Pages.
- No external font files are loaded for the styles themselves; everything is native Unicode characters, so output works anywhere Unicode text is supported (some styles rely on astral-plane characters like mathematical alphanumeric symbols, which render fine in modern browsers/apps but occasionally show as boxes on very old systems).

---

*Part of the [ad0rkableg33k](https://github.com/ad0rkableg33k) creative universe — see also [Unsolicited Deck Pics](https://ad0rkableg33k.github.io/Nightwood-Oracle/) and [Reality is Buffering](https://ad0rkableg33k.github.io/realityisbuffering/).*
