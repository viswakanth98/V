# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **static single-page portfolio website** for a DevOps engineer. There is no build process, no package manager, and no dependencies — just HTML, CSS, and vanilla JavaScript served directly.

## Development

Open `index.html` directly in a browser, or serve it with any static file server:

```bash
python3 -m http.server 8080
# or
npx serve .
```

There are no lint, test, or build commands.

## Architecture

### File Layout

- `index.html` — entire page structure (one HTML file, ~500 lines)
- `css/style.css` — all styles; uses CSS custom properties for the design system
- `js/main.js` — all interactivity; pure vanilla JS, no frameworks
- `assets/` — profile image, favicon, and resume PDF

### Design System (css/style.css)

The stylesheet defines a dark-theme design system via CSS variables at the top of the file:
- Background: `#0a0e1a` (dark navy)
- Primary accent: `#00d4ff` (cyan)
- Secondary accent: `#7c3aed` (purple)
- Font families: Inter (body), Fira Code (monospace/code)

All colors, spacing, shadows, and transitions are derived from these variables — update them to retheme the entire site.

### JavaScript Modules (js/main.js)

`main.js` contains several self-contained features, each clearly commented:
1. **Navbar** — scroll detection, active-link tracking, mobile hamburger
2. **Typed text** — cycles through job titles character-by-character
3. **Particle canvas** — hero background animation using Canvas API; pauses via `IntersectionObserver` when off-screen
4. **Scroll reveal** — lightweight AOS alternative using `IntersectionObserver`
5. **Counters** — animates stat numbers with easeOutExpo easing
6. **Skill bars** — fills percentage bars when scrolled into view
7. **Cursor glow** — radial gradient trail on hero section mouse move

### Content Updates

All content (name, job titles, skills, experience, education, certifications) lives directly in `index.html` — search for the relevant section heading (e.g., `id="experience"`) to locate and edit it. The typed text job titles are defined in the `roles` array at the top of `js/main.js`.
