# Geocities Skill

A Claude Code skill that generates authentically terrible 1998-era personal websites. Table layouts, `<marquee>` tags, Comic Sans, animated GIF dividers, hit counters, guestbooks, webrings, and auto-playing MIDI references. The full Geocities experience.

## What It Does

Give it a topic — a person, hobby, pet, band, conspiracy theory, recipe collection, anything — and it generates a complete standalone HTML file that looks like it was hand-coded in Notepad on Windows 98 and uploaded via FTP to a Geocities subdirectory.

The output is a single `.html` file. No build tools. No frameworks. No dignity.

## Setup

Copy `SKILL.md` into your Claude Code project or reference it in your system prompt. Keep `GIF-CATALOG.md` in the same directory — the skill reads it before generating any HTML to select real GIFs by category.

## Quick Start

```
Generate a 1998-style personal website about [YOUR TOPIC]
```

Options:
- **Neighborhood**: Area51, SunsetStrip, Heartland, SiliconValley, etc.
- **Mood**: earnest, unhinged, wholesome, paranoid
- **Specific elements**: "include a Craig rivalry", "make the cat the CEO"

## Files

```
SKILL.md          — The skill prompt
GIF-CATALOG.md    — ~320 real GIF hashes across 29 categories
examples/         — Example output pages
```

## GIFs

Every generated page uses **real animated GIFs** from [gifcities.org](https://gifcities.org) — the Internet Archive's Geocities GIF collection. Minimum 15 per page. No CSS substitutes, no SVG placeholders, no emoji standing in for the real thing.

`GIF-CATALOG.md` contains ~320 hashes across 29 categories:

**Chrome** — fire, sparkles, dividers, globes, under construction, money, email, welcome, guestbook, awards, counters, Netscape badges, computer/tech

**Topic-specific** — cats, dogs, space/aliens, music/guitar, food, dragons/fantasy, hearts/rainbow, skulls/punk, sports, flowers/butterflies, explosions, angels/fairies, lightning/storm, medieval/scrolls, flags/USA, clocks

The skill reads the catalog first, assigns GIFs by category to specific page locations (banner flanks, dividers, footer badges, topic spots), then builds the HTML around them.

## Example

The `examples/` directory contains a complete two-page Geocities site for **Firestar Digital**:

- `firestar-digital-splash.html` — Splash/enter page
- `firestar-digital.html` — Full site with all the chaos

Features: dollar sign cursor trail, animated starfield, falling gold coins, three marquees, right-click protection, secret password section, live clock, status bar scroller, guestbook with rival character (Craig), webring, self-awarded site awards.

## Live Demo

[firestar-geocities.vercel.app](https://firestar-geocities.vercel.app)

## Philosophy

The page author is **sincere**. They are not being ironic. They learned HTML from "view source" on other Geocities pages and a printed copy of "HTML for Dummies." They are genuinely proud of this website. They think the cursor trail is cutting-edge. They apologize for the page being "under construction" even though it has been under construction since 1997.

The goal is not parody — it's reverence. These pages had soul.
