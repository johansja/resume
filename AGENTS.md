# Resume — Repo Instructions

## What this is

Static single-page resume (`index.html`) for Johan Sim. Deployed to GitHub Pages at https://johansja.github.io/resume/. No build step, no framework, no package manager.

## Editing

Edit `index.html` directly. Pico.css v2 is loaded via CDN (`<link>` in `<head>`) — do not vendor it. Structure:

- `<nav class="topnav">` — sticky nav with scroll-spy anchors; the `.navlinks` anchors and the `IntersectionObserver` ID array at the bottom must stay in sync (add/remove a section in both places).
- `<header class="hero">` — name, title, lede, contact chips.
- `<section id="experience">` — `<ol class="timeline">` of roles; each `<li>` is one role.
- `<section id="skills">` — `.skill-grid` of chip groups.
- Print CSS (`@media print`) flattens to a clean printable resume — keep changes print-safe (no fixed heights, no `position: sticky` inside roles).

PII (phone, email, location) lives in the hero contact chips. Change only when the user asks; do not copy it elsewhere.

## Deploy

Push to `main` → `.github/workflows/deploy.yml` stages `index.html` into `_site/` and deploys to GitHub Pages. No preview branch, no staging — `main` is the live site.

## Commits

History uses natural-language subjects (`Update resume: …`, `Add contact icons …`). No Conventional Commits. No AI attribution trailers.
