# Founding Cohort Landing Page

Standalone landing page for ScalePaid's Founding Cohort offer. Drop this folder into the root of `scalepaid-reddit-system` and GitHub Pages will serve it at:

**Live URL:** `https://futureundefined.github.io/scalepaid-reddit-system/founding-cohort/`

## What's in here

- `index.html`: the full landing page (single file, all CSS inline)
- `ben.jpg`: founder photo (you need to add this; see below)
- `CLAUDE.md`: context for Claude Code working inside this folder
- `README.md`: this file

## Quick deploy (3 commands from the repo root)

```bash
# 1. Make sure you're on main and up to date
git checkout main && git pull

# 2. Drop the folder in (you can do this with Finder/Explorer too)
cp -r /path/to/founding-cohort .

# 3. Add the founder photo, then commit
cp /path/to/your/photo.jpg founding-cohort/ben.jpg
git add founding-cohort/
git commit -m "feat: add Founding Cohort landing page"
git push origin main
```

GitHub Pages will rebuild automatically. Page goes live in ~30 to 90 seconds at the URL above.

## Add the founder photo

The page references `ben.jpg` in this folder. Save your photo as exactly `ben.jpg` (case-sensitive on GitHub Pages) inside `founding-cohort/`.

Recommended:
- Square or 4:5 portrait
- 800px on the long edge or larger
- Under 300 KB after compression (use [squoosh.app](https://squoosh.app) if needed)

If you'd rather use a different filename or `.png`, edit line 778 of `index.html`:
```html
<img src="ben.jpg" alt="Ben Dankiw, Founder of ScalePaid">
```

## Update the spot count

When a brand signs and you go from 4 to 3 spots, update these spots in `index.html`:
- Sticky bar at the top (line ~538): `4 of 5 spots remaining`
- Hero card stat (line ~597): `<div class="num">4</div>`

## Test locally before pushing

```bash
cd founding-cohort
python3 -m http.server 8000
# open http://localhost:8000 in your browser
```

## Maintenance

- **Hard close:** June 30, 2026. After that date, either redirect this URL or replace the page with a "cohort closed, here's what happened" recap.
- **Typeform link:** `https://form.typeform.com/to/lf3pnicO`. If it changes, search/replace in `index.html`.
- **Brand colors and fonts:** Inline in the `<style>` block. The `:root` CSS variables at the top match the ScalePaid brand sheet.
