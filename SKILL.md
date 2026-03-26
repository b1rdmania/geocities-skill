# Geocities Skill

> Generate authentically terrible 1998-era personal websites. Table layouts, `<marquee>` tags, Comic Sans, animated GIF dividers, hit counters, guestbooks, webrings, and auto-playing MIDI references. The full Geocities experience.

## What This Skill Does

Takes a **topic or URL** and generates a complete standalone HTML file that looks like it was hand-coded in Notepad on Windows 98 and uploaded via FTP to a Geocities subdirectory.

Two modes. Both fun.

The output is a single `.html` file. No build tools. No frameworks. No dignity.

---

## Mode Selection

**Ask the user (or infer from their prompt) which mode they want before generating:**

### Fan Page Mode
The page is written by a **sincere superfan** of the topic or brand. They discovered it, their life changed, and now they have a Geocities page about it. Invented persona, fictional guestbook entries from other fans, personal commentary ("I first heard about Yearn in DeFi Summer 2020 and I have never been the same"), and genuine enthusiasm.

Use when: user gives a topic/brand name, asks for a "fan page", or the prompt implies a persona.

### Replica Mode
Take the **actual content and structure of a real website** and render it as if it was built in 1998. Same sections, same copy, same logo colors — but with table layouts, `<font>` tags, marquees, and GIFs. The homepage nav becomes a Geocities nav table. The hero becomes a `<center>` banner with fire GIFs. The brand's real color palette gets geocities-ified (same hues, cranked up to garish).

Use when: user provides a URL, asks to "geocities-ify [site]", or asks for a "1998 version of [brand]".

**If it's ambiguous, ask:** "Do you want a fan page (sincere superfan persona) or a 1998 replica of the actual site?"

---

## Invocation

```
Generate a 1998-style personal website about [TOPIC]          → Fan Page mode
Geocities-ify https://example.com                             → Replica mode (fetch URL first)
Make a 1998 replica of [brand]                                → Replica mode
Make a fan page for [brand/topic]                             → Fan Page mode
```

The user may also provide:
- A specific Geocities "neighborhood" (SunsetStrip, Area51, Heartland, etc.)
- A mood (earnest, unhinged, wholesome, paranoid)
- Specific elements they want included

---

## Brand Extraction (for URL-based requests)

When the user provides a URL, **fetch and extract brand assets before writing any HTML**:

### Step 1: Fetch the page
```
WebFetch the URL and parse the HTML
```

### Step 2: Extract colors
Look for these in order:
- `<meta name="theme-color" content="#XXXXXX">` — the brand's primary color
- CSS custom properties in `<style>` blocks: `--color-primary`, `--brand`, `--accent`, etc.
- `og:image` meta tag URL — note the visual context
- Inline `background-color` or `color` on `<body>` or major layout elements

### Step 3: Extract the logo/favicon
Try these paths in order until one works:
1. `<link rel="icon">` or `<link rel="apple-touch-icon">` in the `<head>`
2. `/apple-touch-icon.png`
3. `/favicon.ico`
4. OG image from `<meta property="og:image">`
5. Any `<img>` with "logo" in the src or alt attribute

**Use the real logo/favicon as an `<img>` tag** in the page header. A tiny pixelated favicon at 64x64 looks very 1998. The OG image can be used as a "site banner."

### Step 4: Geocities-ify the color palette
Take the extracted hex colors and adapt them:
- Keep the hue, but push brightness and saturation to garish extremes
- Dark brand color → use as background, add neon version as text/border color
- Brand accent → use for headers and marquee text
- Add at least one clashing color from the classic Geocities palette that wasn't in the original

Example — Yearn Finance (#000000 bg, blue accents):
- Background: #000033 (dark navy, preserved)
- Text: #00CCFF (neon cyan, Geocities-ified blue)
- Accent: #FFD700 (gold — clashing addition)
- Links: #9966FF (purple — another clash)

---

## Voice & Persona

### Fan Page Mode
The page author is **sincere**. They are not being ironic. They learned HTML from "view source" on other Geocities pages and a printed copy of "HTML for Dummies." They are genuinely proud of this website. They think the cursor trail is cutting-edge. They apologize for the page being "under construction" even though it has been under construction since 1997.

Key tonal markers:
- Third-person self-references ("Welcome to Dave's World of Reptiles!")
- Excessive exclamation marks
- Apologetic tone about unfinished sections
- Casual oversharing of personal information
- Treats the guestbook like social media
- Random capitalization for emphasis
- Updates noted with exact dates ("Last updated: March 14th, 1998 at 2:34am!!")

### Replica Mode
The page reads like the **official website** — same copy, same sections — but rendered by someone who clearly learned HTML from a library book in 1998. No invented persona. The guestbook entries are from real-sounding customers/users. The "about us" section uses the company's real voice, just in Comic Sans on a tiled starfield.

---

## Required Elements

Every generated page **MUST** include ALL of the following:

### 1. Document Structure & Social Meta Tags
```html
<html>
<head>
<title>~*~ [TOPIC] ~*~ Welcome to [NAME]'s [TOPIC] Page!!! ~*~</title>
<meta name="theme-color" content="[brand bg color]">
<meta property="og:title" content="[DEGEN TITLE — see rules below]">
<meta property="og:description" content="[DEGEN DESCRIPTION — see rules below]">
<meta property="og:image" content="og.png">
<meta property="og:type" content="website">
<meta name="twitter:card" content="summary_large_image">
<meta name="twitter:title" content="[DEGEN TITLE]">
<meta name="twitter:description" content="[DEGEN DESCRIPTION]">
<meta name="twitter:image" content="og.png">
</head>
```
- No `<!DOCTYPE>`. No `<meta charset>`. This is 1998.
- `<body>` tag with `bgcolor`, `text`, `link`, `vlink`, `alink` attributes
- Tiled background using a `background` attribute (use a data URI for a small tiled pattern)
- `og:image` is `og.png` (relative) — the user will add the screenshot after publishing

#### OG Title Rules — Degen Geocities Style

The `og:title` and `twitter:title` must be written in authentic Geocities degen style. This is what shows in Telegram/Twitter link previews — it should look unhinged in the best way.

**Fan Page mode** — persona-first, hyperbolic:
```
*~* [PERSONA]'s [TOPIC] FAN PAGE!!! *~* :: The BEST [TOPIC] Site on the INTERNET
~*~ WELCOME TO MY [TOPIC] SHRINE ~*~ :: [NEIGHBORHOOD] Geocities
```

**Replica mode** — brand stat-heavy, ALL CAPS key terms, separators:
```
*~* [BRAND] *~* :: [TAGLINE] :: [KEY STAT] :: Est. 1998
~*~ [BRAND NAME] *~* [NEIGHBOURHOOD] :: [HERO COPY] :: [METRIC]!!!
```

Examples:
- `*~* YEARN FINANCE *~* :: $326M TVL :: Earn on your Crypto :: Est. 1998`
- `~*~ YFI_MAXI_2020's YEARN FAN PAGE ~*~ :: The BEST DeFi Site on The INTERNET!!!`
- `*~* STRIPE *~* :: Payments Infrastructure for the Internet :: WallStreet Neighborhood`
- `~*~ Dave CryptoApe98's BLOCMATES SHRINE ~*~ :: East London's #1 Alpha Source!!!`

#### OG Description Rules — Degen Geocities Style

The description should read like a Geocities page author wrote it — excited, over-punctuated, mixing real info with absurd 1998 energy. Max ~155 chars for display, but write it hot.

**Fan Page mode:**
```
[PERSONA] from [LOCATION] presents: THE GREATEST [TOPIC] FAN PAGE!! Signed guestbooks: [number] :: Under construction since [year] :: PLEASE SIGN MY GUESTBOOK!!!
```

**Replica mode** — lead with the hero stat/tagline, then key features, then excitement:
```
[HERO STAT OR TAGLINE]!! :: [FEATURE 1] :: [FEATURE 2] :: [FEATURE 3] :: Best viewed in Netscape 4.0!!
```

Examples:
- `$326,396,246 deposited in Yearn Vaults!! :: yCRV :: LP Token Vaults :: veYFI :: Earn on your Crypto!! Best viewed in Netscape 4.0`
- `THE BEST DeFi site on the INTERNET made by YFI_Maxi_2020 from London!! Sign my guestbook plz!!!`
- `17,000 newsletter readers can't be wrong!! :: The Alpha :: The Meal Deal :: Way of the Ape :: WAGMI!!!`

### 2. The Welcome Banner
- A `<center>` block at the top
- `<font>` tag with `face="Comic Sans MS"` or `"Papyrus"` and `size="6"` or `size="7"`
- The page title in a garish color
- Flanked by sparkle/star decorations using unicode: `*~*`, `+:.*.:+`, `*.+`, or `~*~`
- In **Replica mode**: include the real logo/favicon as an `<img>` tag
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

---

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
- **Paris** — international, travel, community
- **CollegePark** — community portals, webrings, directories

---

## Page Archetypes

Pick one **before writing any HTML**. The archetype determines the structure — not just colors.

| Archetype | What it is | Layout | Nav style | Divider style |
|---|---|---|---|---|
| **Fan Shrine** | Tribute to a person, band, protocol, or show | Single column, stacked sections, gallery rows | Horizontal strip or none | Rainbow bars, fire |
| **Community Portal** | Webring, directory, or community hub | Full-width sections, member tile grid, classifieds listings | Quick-link strip (no sidebar) | Chain dividers |
| **Financial Service** | Protocol, product, or financial tool | Two-column with stats sidebar, authoritative data tables | Sidebar nav | Gradient bars, lightning |
| **News Zine** | Blog, newsletter, or editorial | Dated entry list, headline hierarchy | Strip or none | Thin animated bars |
| **Personal Homepage** | Someone's "home on the web" | About me box, links sidebar, hobbies/pets sections | Sidebar | Rainbow bars |
| **Tech Reference** | Docs, tool, or developer resource | Monospaced code blocks, badge rows | Strip | Tech/circuit dividers |

The default trap is using a Financial Service layout (2-col + sidebar) for every page regardless of what the site is. Match the archetype to the site.

---

## Color Rules

### Fan Page Mode
Choose from the classic web-safe garish palette. Combine at least 3 that clash:

```
Background favorites:  #000000, #000033, #330066, #003300, #660000, #FFFF00, #FF00FF, #00FFFF
Text favorites:        #FFFFFF, #00FF00, #FF0000, #FFFF00, #00CCFF, #FF00FF, #FF6600
Link favorites:        #0000FF, #00FF00, #FF00FF, #00CCFF
Accent favorites:      #FF0000, #FFFF00, #00FF00, #FF00FF, #FF6600
Table bg favorites:    #333333, #000066, #003300, #330033, #333300, #663300
```

The colors should make a modern designer physically uncomfortable.

### Replica Mode
Start from the brand's extracted colors, then push them to Geocities extremes:
- Preserve the brand hue so it's recognizable
- Crank saturation and brightness
- Add at least one clashing accent color that wasn't in the original brand

---

## Typography Rules

- `<font face="Comic Sans MS, Papyrus, cursive">` for headers
- `<font face="Times New Roman, serif">` for body text
- `<font face="Courier New, monospace">` for "code" or "hacker" sections
- `size` attribute: use `1` through `7`, with headers at `5`-`7`
- **Never use CSS for fonts.** Always `<font>` tags.
- Nest `<font>` tags inside other `<font>` tags for extra authenticity

---

## Layout Rules

- **Everything in tables.** The outer layout is a table. Content blocks are tables. The nav is a table. Tables inside tables.
- `<center>` wraps most things
- `<br><br><br>` is how you add vertical spacing
- `align="center"` on `<td>` and `<p>` elements
- `width="600"` on the main layout table (fixed pixel widths)
- `cellpadding="5"` and `cellspacing="0"` or vice versa
- `border="1"` on tables that shouldn't have borders
- `border="0"` on tables that structurally need them

---

## Background Patterns

Generate a tiled background as an inline SVG data URI. Options:

- **Stars on dark blue**: Small white/yellow dots on #000033
- **Tiny tiles**: Repeating 8x8 pixel checkerboard or diagonal pattern
- **Space theme**: Dark with small colored dots (Area51)
- **Hearts**: Small hearts on a dark background (Heartland)
- **Matrix-style**: Green characters on black (SiliconValley)

Encode as a small SVG and use as `background="data:image/svg+xml,..."` on the `<body>` tag.

---

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

For **Replica mode**, customise the trail symbol to match the brand — `$` for a finance site, `*` for a tech site, etc.

---

## Falling Snow/Particles Implementation

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

---

## GIFs

**MANDATORY: Every page MUST use real animated GIFs from blob.gifcities.org. This is non-negotiable.**

The difference between a convincing Geocities page and a modern imitation is the GIFs. CSS animations, inline SVGs, emoji, unicode characters, and text art are NOT substitutes for real GIFs. If the page has no real `<img src="https://blob.gifcities.org/...">` tags, it has failed.

### Primary Source: GIF-CATALOG.md

**Read `GIF-CATALOG.md` before generating any HTML.** It contains ~320 curated GIFs across 29 categories with full hashes ready to use. The base URL is:

```
https://blob.gifcities.org/gifcities/[HASH].gif
```

Every page should use **at least 15-20 GIFs** from the catalog across multiple categories: fire/flames, sparkles, dividers, under construction, welcome banners, globes, badges, and topic-specific imagery.

For **Replica mode**, select GIFs that match the brand's domain — finance site gets money/coins/gold, tech site gets computers/tech/lightning, etc.

### Thematic GIF Selection

**Before writing any HTML**, pick 3-4 primary GIF categories from the catalog based on the site's domain. Draw 80%+ of your GIFs from these categories only. The remaining 20% can be generic Geocities chrome (sparkles, guestbook, Netscape badges, hit counter).

| Site type | Primary categories | Avoid |
|---|---|---|
| Travel / community / nomads | Globe, Clocks, Flags, Stars | Money, Fire, Construction |
| Finance / DeFi / trading | Money, Lightning, Fire, Stars | Globes, Hearts, Nature |
| Tech / developer tools | Computer, Lightning, Stars, Under Construction | Money, Hearts, Dragons |
| Music / entertainment | Music, Stars, Hearts, Fire | Money, Computer, Flags |
| Food / cooking | Food, Flowers, Stars, Hearts | Computer, Fire, Skulls |
| Fantasy / gaming | Dragons, Angels, Lightning, Stars | Money, Food, Flags |
| Community / social | Hearts, Stars, Welcome, Guestbook | Skulls, Construction |
| Punk / edgy / crypto anon | Skulls, Fire, Lightning, Explosions | Hearts, Angels, Flowers |

**The default trap**: reaching for Fire + Money + Awards + Construction on every single page. That is the generic mix. If the site has nothing to do with finance or construction, those GIFs should not appear.

### Finding Additional GIFs

The gifcities.org website is a JavaScript app — fetching it directly will not return GIF URLs. To find GIFs beyond the catalog, use WebSearch to find gifcities.org blob URLs by keyword. Do not attempt to fetch gifcities.org/search directly.

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

---

## Splash Page (Optional)

For maximum authenticity, generate a separate splash page (`index.html`) that links to the main page (`main.html`). The splash page should be minimal:
- Title with fire GIFs
- Tagline
- Big "ENTER" button/link
- Copyright line
- Same starfield background

---

## Generation Process

1. **Read `GIF-CATALOG.md`** — load the full catalog before writing a single line of HTML.
2. **Determine mode** — Fan Page or Replica. Ask if unclear.
3. **Select archetype** — Fan Shrine, Community Portal, Financial Service, News Zine, Personal Homepage, or Tech Reference. This determines the HTML skeleton, nav style, and divider style. Do not default to Financial Service layout.
4. **Select 3-4 primary GIF categories** from the thematic table above based on the site's domain. Write them down. Draw 80%+ of GIFs from these categories only.
5. **If Replica mode and URL provided**:
   - Fetch the URL and extract all text content and section structure
   - Extract brand colors from `<meta name="theme-color">`, CSS vars, inline styles
   - Extract logo/favicon from `<link rel="icon">`, `apple-touch-icon`, OG image, or logo img tag
   - Geocities-ify the color palette (preserve hue, push to garish, add one clashing accent)
6. **Assign neighborhood** based on topic/brand category
7. **Choose color scheme** — extracted brand colors (Replica) or clashing palette (Fan Page)
8. **Choose background** — tiled SVG starfield as data URI on `<body background="...">`
9. **Generate page author persona** (Fan Page) or map real site sections (Replica)
10. **Draft OG title and description** — write them in degen Geocities style before writing any HTML (see rules in Required Elements § 1). The og:image is `og.png` (relative placeholder).
11. **Plan GIF placement** — assign your chosen 3-4 category GIFs to: welcome banner flanks, section dividers, footer badges, topic-specific spots. Check the thematic GIF table — do not use off-category GIFs as filler.
12. **Build the HTML** — structure matches the chosen archetype. Using ONLY `<table>`, `<font>`, `<center>`, `<br>`, `<hr>`, `<marquee>`, `<blink>`, `<img>` and other period-appropriate tags. Real GIFs in every section. Real logo in header for Replica mode. OG meta tags in `<head>`.
13. **Add interactivity** — cursor trail (topic-themed symbol for Replica) + at least one other JS element
14. **Write earnest, unironic copy** — sincere superfan (Fan Page) or straight site content in 1998 aesthetic (Replica)
15. **Count GIFs** — verify the page has at least 15 real `<img src="https://blob.gifcities.org/...">` tags before finishing

---

## Output

A single HTML file (or two files if splash page included) saved to `~/Downloads/[topic-slug]-geocities.html`

The file should be openable in any modern browser and look authentically terrible. The goal is not parody — it's **reverence**. These pages had soul. We're bringing that soul back, one `<marquee>` at a time.

### After Publishing (here.now or any static host)
Once the user has a public URL, they can:
1. Take a screenshot of the top of the page (1200x630)
2. Upload it as `og.png` alongside `index.html`
3. The social preview will show the actual Geocities page — which looks incredible in a Telegram link unfurl

---

## Example Invocations

```
Generate a 1998-style personal website about my hamster collection
Generate a 1998-style personal website about alien conspiracies (mood: paranoid)
Generate a 1998-style personal website about Andrew Lloyd Webber (neighborhood: Hollywood)
Make a Geocities replica of https://stripe.com
Geocities-ify https://yearn.fi
Make a 1998 fan page for Yearn Finance
Make a 1998 replica of https://linear.app
```

---

## Iron Laws

1. **Read GIF-CATALOG.md first.** Every time. Before any HTML.
2. **Minimum 15 real GIFs** from blob.gifcities.org per page. Count them.
3. **No CSS substitutes for GIFs.** No SVG animations, no CSS keyframes, no emoji standing in for animated GIFs.
4. **No modern HTML.** No `<!DOCTYPE>`, no `<header>`, no `<nav>`, no semantic tags.
5. **No CSS classes or stylesheets.** Inline `<font>` tags and element attributes only.
6. **No flexbox or grid.** Tables only.
7. **No responsive design.** Fixed 600px width.
8. **The author is sincere.** Never ironic. In Replica mode, the brand is sincere.
9. **No modern JavaScript.** `var`, `document.write`, string concatenation. No `const`, `let`, arrow functions.
10. **No `<!DOCTYPE html>`.** This is 1998.
11. **Ask about mode if unclear.** Fan Page or Replica — they produce different outputs.
12. **Extract brand assets for Replica mode.** Fetch the URL, pull colors and logo, use them.
13. **OG meta tags on every page.** Title and description in degen Geocities style. og:image as `og.png`.
14. **Pick an archetype before writing HTML.** Structure follows archetype, not a default template.
15. **Pick 3-4 GIF categories before placing any GIFs.** 80%+ of GIFs come from those categories. No off-category filler.

---

## Anti-Patterns (Things to AVOID)

- **Do NOT use CSS classes or stylesheets.** Inline attributes and `<font>` tags only.
- **Do NOT use semantic HTML.** No `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`.
- **Do NOT use flexbox or grid.** Tables only.
- **Do NOT use responsive design.** Fixed 600px width. If it doesn't fit your screen, that's your problem.
- **Do NOT be ironic.** The page is sincere — whether a fan or the brand itself.
- **Do NOT use modern JavaScript.** No `const`, `let`, arrow functions, template literals.
- **Do NOT include `<!DOCTYPE html>`.** This is 1998.
- **Do NOT substitute CSS animations, inline SVGs, unicode sparkles, or emoji for animated GIFs.** Real GIFs or nothing.
- **Do NOT skip GIF-CATALOG.md.** If you haven't read it, you don't know what GIFs are available. Read it first.
- **Do NOT generate a page with fewer than 15 real blob.gifcities.org img tags.**
- **Do NOT invent a persona for Replica mode.** Use the brand's real voice, just in 1998 aesthetics.
- **Do NOT ignore brand colors in Replica mode.** Extract them, use them, geocities-ify them.
- **Do NOT write a boring og:title.** `*~*` and `::` separators are mandatory. Make it unhinged.
- **Do NOT use the same HTML skeleton for every page.** A community portal and a financial service look nothing alike. Pick the archetype first.
- **Do NOT scatter random GIFs from every category.** Pick 3-4 thematic categories and stick to them. A travel site does not need money bags. A finance site does not need dragons.
- **Do NOT default to rainbow `<hr>` dividers everywhere.** Use chain dividers for journey/travel themes, gradient bars for finance, fire dividers for hype — match the divider to the archetype.
