# Portfolio Site — Claude Context

Personal portfolio for **Birender Singh** (Senior Principal Consultant, Slalom, Melbourne). Engineering and delivery leadership focus.

## What This Is

A single-page static site. The entire site lives in **`index.html`** — all HTML structure, CSS (including custom properties and responsive breakpoints), and JavaScript are in that one file. There is no build step, no npm, no framework, no bundler.

## Tech Stack

- Pure HTML5 / CSS3 / vanilla JS
- Google Fonts CDN: `DM Serif Display` (headings), `Source Sans 3` (body)
- No external JS libraries
- No package.json, no node_modules

## Running Locally

```bash
open index.html
# or
python3 -m http.server 8080
```

Fonts won't render correctly without an internet connection (loaded from Google Fonts CDN).

## Architecture Notes

- **Design tokens** are CSS custom properties defined in `:root` (lines 9–31). Edit colours there, not inline.
- **Scroll reveal** is handled by `IntersectionObserver` in the `<script>` block at the bottom. Elements get class `reveal`; JS adds `visible` when they enter the viewport.
- **Mobile nav** is toggled by adding/removing the `open` class on `.nav-links` via a hamburger `<button>`.
- **Sections** follow the pattern: `section-label` (small caps) → `section-title` (serif heading) → content. Keep new sections consistent.
- **Contact form** is purely front-end — `onsubmit` disables the button and shows a confirmation message. There is no backend or form service wired up.

## Branching Workflow

- `dev` — working branch for all changes
- `main` — production; deployed to GitHub Pages
- Merge `dev` → `main` when ready to publish

## GitHub Repo

`https://github.com/singhbirender88/portfolio-site`

## Content Sections

1. **Hero** — tagline, animated fade-up, CTA to contact
2. **About** — two-column: bio text + detail grid (role, industries, experience, location)
3. **Experience** — three entries: Slalom (2021–present), NAB (2017–2021), Earlier Career (2010–2017)
4. **Skills** — 3-column grid of 6 capability cards with inline SVG icons
5. **Education & Certifications** — 3 edu cards + 4 cert badges
6. **Contact** — dark stone background panel; LinkedIn link + static contact form

## Content Pipeline

All site copy lives in **`CONTENT.md`** — it is the single source of truth. `index.html` should always reflect what's in `CONTENT.md`.

CV PDFs go in **`docs/`**. When a new one is added, follow this process:

### When a new CV PDF is added to docs/

1. **Read the PDF** — use the Read tool on the new file in `docs/`
2. **Update `CONTENT.md`** — reconcile any changed copy (role titles, dates, bio text, skills, certifications, education) with what's in the PDF. Preserve the existing markdown structure; only update values that differ.
3. **Update `index.html`** — apply the same changes from step 2 to the corresponding sections in `index.html`. The section layout and CSS classes should not change; only the text content inside them.
4. **Commit on `dev`** — stage `CONTENT.md` and `index.html` together with a message like `Update content from CV — <filename>`.

### Manual trigger

To kick this off, tell Claude Code:
> "I've added `docs/<filename>.pdf` — update the site content from it."

### File roles

| File | Purpose |
|------|---------|
| `docs/*.pdf` | Source CV documents — drop new ones here |
| `CONTENT.md` | Structured markdown mirror of all site copy |
| `index.html` | The rendered site — always kept in sync with `CONTENT.md` |

---

## What to Watch Out For

- Editing CSS: all styles are in a single `<style>` block in `<head>`. Search for the relevant class name before adding new rules.
- The `exp-meta` column uses `position: sticky` on desktop — don't add `overflow: hidden` to parent containers or it will break.
- Font sizes use `clamp()` for responsive headings — prefer this pattern for new large text.
