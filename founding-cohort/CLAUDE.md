# Claude Code instructions: founding-cohort/

This folder is the Founding Cohort landing page for ScalePaid. It's a single-file static page deployed via GitHub Pages.

## What this page is
A 90-day Reddit Ads pilot offer for 5 hand-picked brands at $1,500/mo flat. Hard close: June 30, 2026. Apply CTA points to `https://form.typeform.com/to/lf3pnicO`.

## Stack
- Single `index.html` with inline CSS, no build step
- Google Fonts: Instrument Serif + Instrument Sans (loaded via CDN)
- No JS dependencies, no localStorage, no external APIs

## Brand system (do not deviate)
CSS variables are declared at the top of `index.html`:
- `--sp-orange-red: #FF4500`: brand identity, headers, accents, link text
- `--sp-black: #0E0F11`: primary background, body text on light
- `--sp-charcoal: #18191D`: alternate dark sections
- `--sp-off-white: #F5F5F0`: light sections only (founder card uses this)
- `--sp-gold: #FDC171`: gradient endpoint only, never standalone
- `--sp-green: #26D100`: semantic only (metrics, checkmarks). Never on headers, CTAs, body.
- `--sp-gradient: linear-gradient(90deg, #FF4500, #FDC171)`: primary CTAs only
- Fonts: `--sp-font-serif` (Instrument Serif) for hero/h1/h2/h4 only, `--sp-font-sans` (Instrument Sans) everywhere else

CTA hierarchy:
- Primary: orange-to-gold gradient, white bold, **pill-shaped** (border-radius: 999px)
- Secondary: white outline, white text, pill
- Tertiary: orange red text + arrow, no container

## Style rules
- No em dashes anywhere. Use periods, commas, colons, or "and" instead.
- Short paragraphs (2 sentences max in marketing copy)
- No buzzwords ("synergy", "leverage", "holistic", "cutting-edge")
- No hedge language ("might", "could potentially", "we believe")
- Active voice always
- Specific over vague: numbers and timelines beat adjectives

## Common tasks

**Update spot count (when a brand signs):**
1. Sticky bar at the top: `4 of 5 spots remaining` → decrement
2. Hero card stat block: the second `<div class="num">4</div>` → decrement
3. FAQ "How fast do I need to decide?" copy
4. Final CTA section if it mentions spot count

**Update Typeform link:**
Search for `form.typeform.com/to/lf3pnicO` and replace. There are 3 instances on the page.

**Replace founder photo:**
Drop new file as `ben.jpg` in this folder. If using a different filename or extension, update the `<img src="ben.jpg">` tag near the founder section.

**Add UTM tracking per channel:**
Append to the Typeform URL, e.g., `?utm_source=linkedin&utm_medium=organic&utm_campaign=founding-cohort`. Different per CTA if needed.

## What not to do
- Don't add a build step. This page must remain single-file.
- Don't introduce JS frameworks. Static HTML only.
- Don't use localStorage or external state.
- Don't change the brand color values. The `:root` block is canon.
- Don't soften the qualifier copy. The "this isn't for you if" list is intentional and load-bearing.
- Don't add hard guarantees. The "soft promise / aligned incentives" framing is deliberate. The line is: "If we don't get you results, we don't get the case study, and we lose with you."

## After June 30, 2026
The cohort closes. Replace this page with a recap (results, named brands, what's next) or 301 redirect to a new offer. Don't leave the live "4 spots remaining" page up after the close date.
