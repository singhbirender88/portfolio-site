# Birender Singh — Portfolio Site

Personal portfolio site for Birender Singh, Senior Principal Consultant at Slalom. Built as a single-page static site showcasing engineering and delivery leadership experience.

**Live site:** [github.com/singhbirender88/portfolio-site](https://github.com/singhbirender88/portfolio-site)

## Overview

A minimal, editorial-style portfolio with sections for About, Experience, Skills, Education & Certifications, and Contact. Designed for a professional audience in consulting, financial services, and public sector contexts.

## Tech Stack

- **HTML/CSS/JS** — single `index.html` file, no build tools, no framework, no dependencies
- **Fonts** — [DM Serif Display](https://fonts.google.com/specimen/DM+Serif+Display) (headings) + [Source Sans 3](https://fonts.google.com/specimen/Source+Sans+3) (body) loaded from Google Fonts CDN
- **Animations** — CSS keyframes for hero fade-up; `IntersectionObserver` for scroll reveal on section content
- **Responsive** — mobile hamburger nav at ≤860px; single-column layouts at ≤540px

## Running Locally

No build step required — open the file directly or serve it:

```bash
# Option 1: open directly in browser
open index.html

# Option 2: local server (avoids any CORS quirks with fonts)
python3 -m http.server 8080
# then visit http://localhost:8080
```

> Note: Google Fonts requires an internet connection for correct font rendering.

## Project Structure

```
portfolio-site/
└── index.html   # entire site — HTML, CSS, and JS in one file
```

## Branching Workflow

| Branch | Purpose |
|--------|---------|
| `main` | Production — deployed to GitHub Pages |
| `dev`  | Active development — merge to `main` when ready to publish |

Changes should be made on `dev` and merged to `main` via pull request.

## Deployment

Deployed as a static site via **GitHub Pages** from the `main` branch. Any push to `main` is reflected live.

## Contact

- LinkedIn: [linkedin.com/in/birendersingh88](https://www.linkedin.com/in/birendersingh88/)
