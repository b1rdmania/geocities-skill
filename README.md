# Geocities Skill

A Claude Code skill that generates authentically terrible 1998-era personal websites. Table layouts, `<marquee>` tags, bold italic serif fonts, animated GIF dividers, hit counters, guestbooks, webrings, and auto-playing MIDI references. The full Geocities experience.

## What It Does

Give it a topic — a person, hobby, pet, band, conspiracy theory, recipe collection, anything — and it generates a complete standalone HTML file that looks like it was hand-coded in Notepad on Windows 98 and uploaded via FTP to a Geocities subdirectory.

The output is a single `.html` file. No build tools. No frameworks. No dignity.

## Setup

### As a Claude Code Skill

Copy `SKILL.md` into your Claude Code project or reference it in your system prompt. The skill will use `GIF-CATALOG.md` as a reference for sourcing real animated GIFs.

### Quick Start

```
Generate a 1998-style personal website about [YOUR TOPIC]
```

Options:
- **Neighborhood**: Area51, SunsetStrip, Heartland, SiliconValley, etc.
- **Mood**: earnest, unhinged, wholesome, paranoid
- **Specific elements**: "include a Craig rivalry", "make the cat the CEO"

## Files

```
SKILL.md          — The skill prompt (the brain)
GIF-CATALOG.md    — Curated GIF collection from gifcities.org with URLs + search instructions
examples/         — Example output pages
```

## GIFs

Every generated page uses **real animated GIFs** from [gifcities.org](https://gifcities.org) — the Internet Archive's searchable Geocities GIF collection. No inline SVG placeholders. The GIFs are what make it feel real.

`GIF-CATALOG.md` contains ~50 curated GIFs across 13 categories (fire, sparkles, under construction, dividers, money, globes, badges, etc.) plus instructions for finding more via the gifcities.org search API.

## Example

The `examples/` directory contains a complete two-page Geocities site for **Firestar Digital** (a fictional trading infrastructure company):

- `firestar-digital-splash.html` — Splash/enter page
- `firestar-digital.html` — Full site with all the chaos

Features demonstrated:
- Dollar sign cursor echo trail (12 fading $ symbols follow the mouse)
- Animated starfield background with shooting stars
- Falling gold coins
- Three simultaneous marquees
- Right-click protection alert
- Secret password section
- Live clock + days-online counter
- Status bar scrolling text
- Guestbook with rival character (Craig)
- Webring navigation
- Self-awarded site awards
- Bold italic serif typography (Georgia) in gold on dark blue

## Live Demo

[firestar-geocities.vercel.app](https://firestar-geocities.vercel.app)

## Philosophy

The page author is **sincere**. They are not being ironic. They learned HTML from "view source" on other Geocities pages and a printed copy of "HTML for Dummies." They are genuinely proud of this website. They think the cursor trail is cutting-edge. They apologize for the page being "under construction" even though it has been under construction since 1997.

The goal is not parody — it's reverence. These pages had soul.
