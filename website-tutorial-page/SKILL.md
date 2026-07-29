---
name: website-tutorial-page
description: Add or edit a BioMedBound page consistent with the site's existing nav, styling, and voice. Use whenever creating or updating a page on the AlinaWebsite/BioMedBound site.
---

# Website tutorial page

Keep new or edited pages consistent with the rest of the BioMedBound site
instead of inventing new markup/style per page.

## Structure

- Start from an existing page as a template (`molecularDocking/Hello1.html`
  or `molecularDocking/softwareInstall.html` are good references for
  tutorial-style pages) rather than writing markup from scratch.
- Reuse the standard structure: `mainDiv` > `titleDiv` + `topLinksDiv` (nav)
  + `topSplashDiv` (intro) + content + `.footer`.
- Reuse existing CSS classes rather than adding new ones unless something
  genuinely new is needed: `.code` for command blocks, `.pageImage` for
  images, `.indexCard`/`.reviewCardDiv` for card layouts, `.pageBodyDiv` for
  prose sections.

## Paths

- **Relative paths only** — never a leading `/`. Root-level pages use
  `styles.css`, `index.html`, etc. Pages one level deep (`toys/`,
  `molecularDocking/`) use `../styles.css`, `../index.html`, etc., and
  same-folder assets are unprefixed (`images/foo.png`).
- Place new images in the relevant subfolder's `images/` directory (e.g.
  `molecularDocking/images/`), not the shared root `images/`, unless the
  asset is genuinely sitewide.

## Nav consistency

- The `topLinksDiv` nav block is duplicated on every page. If a new
  top-level page is added, update the nav block on **every** existing page
  to include it — don't leave pages out of sync.
- While editing a page's nav, double check its existing links are correct
  (there's a known pre-existing bug where some pages link "Science Book
  Reviews" to `index.html` instead of `books.html` — fix it if you're
  already touching that nav block).

## Voice

First-person, high-school-science-blog tone: plainspoken, tutorial-style,
mild humor is fine, but explain jargon rather than assuming it. Match
`molecularDocking/Hello1.html` / `Hello2.html` / `softwareInstall.html`.

## Footer

Every page ends with the same contact block:
`Contact: <a class="link" href="mailto: alinaren@biomedbound.com">AlinaRen@biomedbound.com</a>`

## Scope note

If the page discusses docking results, follow the safety/scope note in
`CLAUDE.md`: present affinity scores as computational predictions, not
clinical claims.
