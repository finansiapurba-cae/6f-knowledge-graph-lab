# 6F Knowledge Graph Lab

An educational website about turning as-built drawings into a knowledge graph, based on
*From As-Built Drawings to a Knowledge Graph: An Introduction to the 6F Baseline Graph*
(Chien-Pu Huang, Oct 25, 2026).

Pages: Home · The story · Lab · Learn · About & sources (one file, linked with `#home`, `#story`, `#lab`, `#learn`, `#about`).

## Files

- `index.html` – the complete website. Self-contained: no build step, no server code, no API key.
- `lab.html` – the same site written as the source for the claude.ai artifact (no `<html>`/`<head>` wrapper).

## Put it online

Any static host works because the site is a single HTML file.

**Netlify Drop (fastest, no account setup beyond sign-in):** open https://app.netlify.com/drop and drag this folder onto the page. You get a public URL straight away.

**GitHub Pages:** create a repository, add `index.html`, then in *Settings → Pages* choose “Deploy from a branch”, branch `main`, folder `/ (root)`. The site appears at `https://<your-user>.github.io/<repo>/`.

**Open locally:** double-click `index.html`.

Fonts load from Google Fonts; everything else is inline. Without internet the page still works with system fonts.
