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
- All nav links, including "Science Book Reviews" → `books.html`, are
  correct sitewide as of this writing — verify they stay that way whenever
  you touch a nav block.

## Card ordering when a new page is added

Whenever a new page is added under Educational Toy Reviews, Science Book
Reviews, or Molecular Docking, **two** places need a new card: the section's
own listing page, and `index.html`'s "most recent updates" row. They order
oldest→newest in opposite directions, so don't copy one pattern to the
other:

- **`index.html`** (`.cardContainer`, `.indexCard`s): always exactly **3**
  cards, the 3 most recent updates across *all* sections combined, oldest to
  newest reading **first-to-last in the HTML source** (which renders
  left-to-right/wrapping, since `.indexCard` is `inline-block`). Adding a
  new page's card here means: build a new `.indexCard` block matching the
  existing format (`<a href="..."><div class="indexCard"><h3>Section
  Name</h3><h4>Page Title</h4><img class="cardImage" .../><div
  class="summary"><p>...</p></div></div></a>`), **append it at the bottom of
  `.cardContainer`** (last in source = newest = rightmost), and **delete the
  first (topmost/oldest) card block** so exactly 3 remain — nothing else
  about the two surviving cards changes, they just end up shifted one
  position toward the front.
- **Section listing pages** (`toys.html`, `books.html`,
  `MolecularDocking.html`): unbounded, newest first. Insert the new card
  (`.reviewCardDiv` format) as the **first** card in the list (right after
  the opening of `.reviewDiv`), pushing every existing card down. Never
  remove a card here — these pages keep the full history.

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
