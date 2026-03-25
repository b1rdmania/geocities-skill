# Geocities Skill

A Claude Code skill that generates authentically terrible 1998-era personal websites. Table layouts, `<marquee>` tags, Comic Sans, animated GIF dividers, hit counters, guestbooks, webrings. The full Geocities experience — for any topic or URL.

## Two Modes. Both Fun.

### Fan Page
Give it a topic or brand. Get a sincere superfan's personal Geocities page about it. Invented persona, fictional guestbook entries from fellow fans, personal commentary, genuine enthusiasm. The author discovered this thing and their life has not been the same since.

```
Make a 1998-style fan page for Yearn Finance
Generate a Geocities page about my hamster collection
```

### Site Replica
Give it a URL. It fetches the real site, extracts the brand colors and logo, maps the actual content and sections, then renders the whole thing as if it was built in 1998. Same copy, same structure — but in Comic Sans on a tiled starfield with fire GIFs flanking the header.

```
Geocities-ify https://stripe.com
Make a 1998 replica of https://linear.app
```

Not sure which you want? The skill will ask.

## Setup

Copy `SKILL.md` into your Claude Code project or reference it in your system prompt. Keep `GIF-CATALOG.md` in the same directory — the skill reads it before generating any HTML to select real GIFs by category.

## Quick Start

```
Generate a 1998-style personal website about [YOUR TOPIC]
Geocities-ify [URL]
```

Options:
- **Neighborhood**: Area51, SunsetStrip, Heartland, SiliconValley, WallStreet, etc.
- **Mood**: earnest, unhinged, wholesome, paranoid
- **Mode**: fan page or replica (or leave it and the skill will ask)

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

## Example

The `examples/` directory contains a complete two-page Geocities site for **Firestar Digital**:

- `firestar-digital-splash.html` — Splash/enter page
- `firestar-digital.html` — Full site with all the chaos

Features: dollar sign cursor trail, animated starfield, falling gold coins, three marquees, right-click protection, secret password section, live clock, status bar scroller, guestbook with rival character, webring, self-awarded site awards.

## Live Demo

[firestar-geocities.vercel.app](https://firestar-geocities.vercel.app)

## Philosophy

The page is always **sincere**. Whether it's a fan writing about their favourite DeFi protocol, or the brand's own 1998 homepage — nobody is winking at the camera. They are genuinely proud of this website. They think the cursor trail is cutting-edge. The goal is not parody — it's reverence. These pages had soul.
