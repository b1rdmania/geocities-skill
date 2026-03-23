# Geocities Skill

> Generate authentically terrible 1998-era personal websites. Table layouts, `<marquee>` tags, Comic Sans, animated GIF dividers, hit counters, guestbooks, webrings, and auto-playing MIDI references. The full Geocities experience.

## What This Skill Does

Takes a **topic** (person, hobby, pet, band, conspiracy theory, recipe collection — anything) and generates a complete standalone HTML file that looks like it was hand-coded in Notepad on Windows 98 and uploaded via FTP to a Geocities subdirectory.

The output is a single `.html` file. No build tools. No frameworks. No dignity.

## Invocation

```
Generate a 1998-style personal website about [TOPIC]
```

The user may also provide:
- A specific Geocities "neighborhood" (SunsetStrip, Area51, Heartland, etc.)
- A mood (earnest, unhinged, wholesome, paranoid)
- Specific elements they want included

## Voice & Persona

The page author is **sincere**. They are not being ironic. They learned HTML from "view source" on other Geocities pages and a printed copy of "HTML for Dummies." They are genuinely proud of this website. They think the cursor trail is cutting-edge. They apologize for the page being "under construction" even though it has been under construction since 1997.

Key tonal markers:
- Third-person self-references ("Welcome to Dave's World of Reptiles!")
- Excessive exclamation marks
- Apologetic tone about unfinished sections
- Casual oversharing of personal information
- Treats the guestbook like social media
- Random capitalization for emphasis
- Updates noted with exact dates ("Last updated: March 14th, 1998 at 2:34am!!")

## Required Elements

Every generated page **MUST** include ALL of the following:

### 1. Document Structure
```html
<html>
<head>
<title>~*~ [TOPIC] ~*~ Welcome to [NAME]'s [TOPIC] Page!!! ~*~</title>
</head>
```
- No `<!DOCTYPE>`. No `<meta charset>`. This is 1998.
- `<body>` tag with `bgcolor`, `text`, `link`, `vlink`, `alink` attributes
- Tiled background using a `background` attribute (use a data URI for a small tiled pattern)

### 2. The Welcome Banner
- A `<center>` block at the top
- `<font>` tag with `face="Comic Sans MS"` or `"Papyrus"` and `size="6"` or `size="7"`
- The page title in a garish color
- Flanked by sparkle/star decorations using unicode: `*~*`, `+:.*.:+`, `*.+`, or `~*~`
- A `<marquee>` with a welcome message or quote

### 3. Navigation
- A `<table>` with `cellpadding`, `cellspacing`, `border` attributes
- `bgcolor` on cells for that classic button look
- Links styled with `<font>` tags
- Sections: Home | About Me | [Topic] | Links | Guestbook | Email Me

### 4. Under Construction
- At least ONE "under construction" notice
- Use unicode construction signs or text art: `[ UNDER CONSTRUCTION ]`
- Apologetic text: "Sorry this page isn't done yet! Check back soon!!"

### 5. Content Area
- All content in nested `<table>` layouts
- `<font>` tags on everything — never CSS
- Liberal use of `<br><br>` for spacing
- `<hr>` with `size="2" noshade` or `color` attributes as section dividers
- `<b>`, `<i>`, `<u>` for emphasis — never `<strong>` or `<em>`

### 6. The Sidebar (or Bottom Links)
- Personal links collection ("Cool Links!!!")
- Mix of dead-sounding URLs and real 90s references
- "Sign my Guestbook!" link
- Webring navigation: `[ Previous | Random | Next | List ]`
- Hit counter: "You are visitor number: **[random 4-5 digit number]**"

### 7. Footer
- "Best viewed in Netscape Navigator 4.0 at 800x600"
- "Made with Notepad" or "Made on a Macintosh"
- Copyright with the person's first name and a year between 1996-1999
- Email link with `mailto:` using a Hotmail, AOL, or Yahoo address
- "This page is hosted by Geocities — get your FREE homepage!"

### 8. Interactive JavaScript
At least TWO of these:
- **Status bar scroller**: Text scrolling in the browser status bar via `window.status`
- **Right-click alert**: `oncontextmenu` that shows "Don't steal my HTML!!"`
- **Alert on load**: Welcome message in an `alert()` box
- **Cursor trail**: Trailing sparkles/stars following the mouse (CSS + JS)
- **Snow/particles**: Falling elements using basic JS animation
- **Clock**: A ticking clock showing the current time
- **Days counter**: "This page has been online for X days!"

## Element Catalog

Draw from these freely. Use at least 8-10 per page:

### Text Effects
- `<marquee>` — scrolling text (use `direction`, `scrollamount`, `behavior` attributes)
- `<blink>` — blinking text (still works in some browsers, include anyway)
- `<font color="rainbow">` — manually alternate colors per letter for rainbow text
- ALL CAPS sections
- Centered poems or song lyrics with `<pre>` or `<br>` breaks
- ASCII art borders

### Visual Decorations
- Horizontal rules: `<hr>` with attributes
- Unicode decorative borders: `*~*~*~*~*~*~*~*~*~*~*`
- Sparkle/star characters: `*.+`, `.:*:.`, `+*+`
- Box-drawing characters for "frames"
- `<table>` cells used as decorative borders with bgcolor

### Classic Content Blocks
- **About Me**: Age, location, favorite color, AIM screen name, star sign
- **My Pets**: Names, breeds, "funny stories"
- **My Awards**: badges/text claiming "Cool Site Award" etc.
- **My Favorite Links**: Links to other Geocities pages, Altavista, Lycos
- **Webrings**: "This [TOPIC] Ring site is owned by [NAME]"
- **Guestbook**: "Please sign my guestbook! I love reading your messages!"
- **MIDI reference**: `<!-- Background music would go here but we can't embed MIDI in 2026 lol -->` with a note like "Turn your speakers on for the background music!"
- **Email Me**: `<a href="mailto:cooldude98@hotmail.com">` with animated envelope text

### Geocities Neighborhoods
Assign based on topic:
- **Area51** — sci-fi, paranormal, conspiracy
- **SunsetStrip** — music, bands, entertainment
- **Heartland** — family, pets, personal
- **SiliconValley** — tech, programming, computers
- **Athens** — education, philosophy, literature
- **EnchantedForest** — kids, fantasy, fairy tales
- **TimesSquare** — games, puzzles, fun
- **WallStreet** — business, finance
- **CapitolHill** — politics, government
- **NapaValley** — food, wine, cooking
- **Hollywood** — movies, celebrities, TV shows

## Color Rules

Choose from the classic web-safe garish palette. Combine at least 3 that clash:

```
Background favorites:  #000000, #000033, #330066, #003300, #660000, #FFFF00, #FF00FF, #00FFFF
Text favorites:        #FFFFFF, #00FF00, #FF0000, #FFFF00, #00FFFF, #FF00FF, #FF6600
Link favorites:        #0000FF, #00FF00, #FF00FF, #00FFFF
Accent favorites:      #FF0000, #FFFF00, #00FF00, #FF00FF, #FF6600
Table bg favorites:    #333333, #000066, #003300, #330033, #333300, #663300
```

The colors should make a modern designer physically uncomfortable. If they don't clash, you've failed.

## Typography Rules

- `<font face="Comic Sans MS, Papyrus, cursive">` for headers
- `<font face="Times New Roman, serif">` for body text
- `<font face="Courier New, monospace">` for "code" or "hacker" sections
- `size` attribute: use `1` through `7`, with headers at `5`-`7`
- **Never use CSS for fonts.** Always `<font>` tags.
- Nest `<font>` tags inside other `<font>` tags for extra authenticity

## Layout Rules

- **Everything in tables.** The outer layout is a table. Content blocks are tables. The nav is a table. Tables inside tables.
- `<center>` wraps most things
- `<br><br><br>` is how you add vertical spacing
- `align="center"` on `<td>` and `<p>` elements
- `width="600"` on the main layout table (fixed pixel widths)
- `cellpadding="5"` and `cellspacing="0"` or vice versa
- `border="1"` on tables that shouldn't have borders
- `border="0"` on tables that structurally need them

## Background Patterns

Generate a tiled background as an inline SVG data URI. Options:

- **Stars on dark blue**: Small white/yellow dots on #000033
- **Tiny tiles**: Repeating 8x8 pixel checkerboard or diagonal pattern
- **Space theme**: Dark with small colored dots (Area51)
- **Hearts**: Small hearts on a dark background (Heartland)
- **Matrix-style**: Green characters on black (SiliconValley)

Encode as a small SVG and use as `background="data:image/svg+xml,..."` on the `<body>` tag.

## Cursor Trail Implementation

Include this JavaScript for a star cursor trail:

```javascript
var trail = [];
var trailLength = 12;
for (var i = 0; i < trailLength; i++) {
  var star = document.createElement('div');
  star.innerHTML = '*';
  star.style.cssText = 'position:fixed;pointer-events:none;font-size:' +
    (20 - i) + 'px;color:' +
    ['#FFD700','#FF69B4','#00FFFF','#FF00FF','#FFFF00','#00FF00'][i % 6] +
    ';z-index:9999;transition:all ' + (i * 0.05) + 's ease;';
  document.body.appendChild(star);
  trail.push(star);
}
document.addEventListener('mousemove', function(e) {
  trail[0].style.left = e.clientX + 'px';
  trail[0].style.top = e.clientY + 'px';
  for (var i = trail.length - 1; i > 0; i--) {
    trail[i].style.left = trail[i-1].style.left;
    trail[i].style.top = trail[i-1].style.top;
  }
});
```

## Falling Snow Implementation

For winter/holiday themes or general whimsy:

```javascript
function makeSnow() {
  var s = document.createElement('div');
  s.innerHTML = ['*','.','+','o'][Math.floor(Math.random()*4)];
  s.style.cssText = 'position:fixed;top:-10px;left:' + Math.random()*100 +
    '%;color:#fff;font-size:' + (8+Math.random()*16) +
    'px;pointer-events:none;z-index:9998;opacity:' + (0.3+Math.random()*0.7);
  document.body.appendChild(s);
  var y = -10, x = parseFloat(s.style.left), drift = (Math.random()-0.5)*2;
  var fall = setInterval(function() {
    y += 1 + Math.random()*2;
    x += drift;
    s.style.top = y + 'px';
    s.style.left = x + '%';
    if (y > window.innerHeight) { s.remove(); clearInterval(fall); }
  }, 50);
}
setInterval(makeSnow, 300);
```

## GIFs

**MANDATORY: Every page MUST use real animated GIFs from blob.gifcities.org. This is non-negotiable.**

The difference between a convincing Geocities page and a modern imitation is the GIFs. CSS animations, inline SVGs, emoji, unicode characters, and text art are NOT substitutes for real GIFs. If the page has no real `<img src="https://blob.gifcities.org/...">` tags, it has failed.

### Primary Source: GIF-CATALOG.md

**Read `GIF-CATALOG.md` before generating any HTML.** It contains ~50 curated GIFs across 13 categories with full hashes ready to use. The base URL is:

```
https://blob.gifcities.org/gifcities/[HASH].gif
```

Every page should use **at least 15-20 GIFs** from the catalog across multiple categories: fire/flames, sparkles, dividers, under construction, welcome banners, globes, badges, and topic-specific imagery.

### Finding Additional GIFs

The gifcities.org website is a JavaScript app — fetching it directly will not return GIF URLs. To find GIFs beyond the catalog, use WebSearch to find gifcities.org blob URLs by keyword, or use additional hashes you know are valid. Do not attempt to fetch gifcities.org/search directly.

### Usage
```html
<!-- Sizes by category -->
<!-- Sparkles/stars: 30-50px -->
<!-- Fire: 80-120px -->
<!-- Dividers: 400-550px wide, use width="100%" -->
<!-- Under construction: 150-200px -->
<!-- Welcome banners: 200-300px -->
<!-- Badges (Netscape etc): 88x31px — the classic web badge size -->
<!-- Globe: 30-120px depending on context -->
<!-- NEW badges: 50-80px wide -->
<!-- Awards: 80-100px -->
<!-- Email: 60-100px -->
```

Place GIFs:
- Flanking the welcome banner (fire, sparkles)
- As section dividers (divider category — use `width="100%"`)
- Under construction notices (construction category)
- In the footer (globe, Netscape badge, Notepad badge)
- Scattered throughout content areas (topic-relevant + general)
- "NEW!" badges next to recently updated sections

## Splash Page (Optional)

For maximum authenticity, generate a separate splash page (`index.html`) that links to the main page (`main.html`). The splash page should be minimal:
- Title with fire GIFs
- Tagline
- Big "ENTER" button/link
- Copyright line
- Same starfield background
- That's it — tease, don't spoil

## Generation Process

1. **Read `GIF-CATALOG.md`** — load the full catalog before writing a single line of HTML. Select GIFs by category for use throughout the page.
2. **Receive topic** from user
3. **Assign neighborhood** based on topic category
4. **Choose color scheme** — 3-4 clashing colors from the palette
5. **Choose background** — tiled SVG starfield as data URI on `<body background="...">`
6. **Generate page author persona** — name, email, AIM screenname, location, year
7. **Plan GIF placement** — assign catalog GIFs to: welcome banner flanks, section dividers, under construction, footer badges, topic-specific spots
8. **Build the HTML** — using ONLY `<table>`, `<font>`, `<center>`, `<br>`, `<hr>`, `<marquee>`, `<blink>`, `<img>` and other period-appropriate tags. Real GIFs in every section.
9. **Add interactivity** — cursor trail + at least one other JS element
10. **Write earnest, unironic copy** — the author loves this website and their topic
11. **Count GIFs** — verify the page has at least 15 real `<img src="https://blob.gifcities.org/...">` tags before finishing

## Output

A single HTML file (or two files if splash page included) saved to `~/Downloads/[topic-slug]-geocities.html`

The file should be openable in any modern browser and look authentically terrible. The goal is not parody — it's **reverence**. These pages had soul. We're bringing that soul back, one `<marquee>` at a time.

## Example Invocations

```
Generate a 1998-style personal website about my hamster collection
Generate a 1998-style personal website about alien conspiracies (mood: paranoid)
Generate a 1998-style personal website about Andrew Lloyd Webber (neighborhood: Hollywood)
Generate a 1998-style personal website about Visual Basic programming
Generate a 1998-style personal website about my dad's chili recipe
```

## Iron Laws

1. **Read GIF-CATALOG.md first.** Every time. Before any HTML.
2. **Minimum 15 real GIFs** from blob.gifcities.org per page. Count them.
3. **No CSS substitutes for GIFs.** No SVG animations, no CSS keyframes, no emoji standing in for animated GIFs.
4. **No modern HTML.** No `<!DOCTYPE>`, no `<header>`, no `<nav>`, no semantic tags.
5. **No CSS classes or stylesheets.** Inline `<font>` tags and element attributes only.
6. **No flexbox or grid.** Tables only.
7. **No responsive design.** Fixed 600px width.
8. **The author is sincere.** Never ironic.
9. **No modern JavaScript.** `var`, `document.write`, string concatenation. No `const`, `let`, arrow functions.
10. **No `<!DOCTYPE html>`.** This is 1998.

## Anti-Patterns (Things to AVOID)

- **Do NOT use CSS classes or stylesheets.** Inline attributes and `<font>` tags only.
- **Do NOT use semantic HTML.** No `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`.
- **Do NOT use flexbox or grid.** Tables only.
- **Do NOT use responsive design.** Fixed 600px width. If it doesn't fit your screen, that's your problem.
- **Do NOT be ironic.** The page author is sincere. They are not doing this as a joke. They genuinely think this website is cool.
- **Do NOT use modern JavaScript.** No `const`, `let`, arrow functions, template literals. Use `var`, `document.write`, `window.status`, and string concatenation.
- **Do NOT include `<!DOCTYPE html>`.** This is 1998. We don't need your fancy document types.
- **Do NOT substitute CSS animations, inline SVGs, unicode sparkles, or emoji for animated GIFs.** Real GIFs or nothing.
- **Do NOT skip GIF-CATALOG.md.** If you haven't read it, you don't know what GIFs are available. Read it first.
- **Do NOT generate a page with fewer than 15 real blob.gifcities.org img tags.** A Geocities page without GIFs is just a bad HTML document.
