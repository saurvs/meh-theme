# Changelog

## 1.0.1 (2026-11-27)

- Code blocks: the `<pre>` is now the bordered box and does the scrolling, so
  a block with long lines no longer loses its right border.
- More space between the `##` sections of `content/_index.md` on the home
  page, matching the spacing of the 2017 layout.

## 1.0.0 (2026-11-27)

First tagged release; the theme was rewritten for current Hugo.

- Requires Hugo 0.158.0 or later (`min_version` in `theme.toml`). CI builds the
  example site with 0.158.0 and the latest Hugo and fails on warnings and
  deprecations.
- Templates use Hugo's current layout structure (`baseof.html`, `home.html`,
  `page.html`, `list.html`, `404.html`, `_partials/`).
- Personal content is no longer hard-coded in the theme: the home page shows
  `content/_index.md`, author links come from `[params.author]` (Hugo removed
  `.Site.Author`), and the "posted by" name is no longer fixed.
- Added list pages for sections (with pagination via `[pagination] pagerSize`)
  and a 404 page; previously these rendered as empty files.
- `<head>`: fixed the unclosed `</head>`; added `<html lang>` from `locale`,
  `<meta name="description">`, a canonical link, the RSS `<link rel="alternate">`
  and `hugo.Generator`; Google Fonts over HTTPS with `display=swap` (optional via
  `disableGoogleFonts`); stylesheet URLs via `relURL` instead of `.Site.BaseURL`;
  optional `_partials/head-extra.html` hook.
- Accessibility: one `<h1>` per page and no skipped heading levels, a `<main>`
  landmark, `<time datetime>` for post dates, link colours that meet WCAG AA
  contrast, a visible focus outline, keyboard-scrollable code blocks, and no
  more `target="_blank"` on links.
- Pages without a date no longer show "posted on Jan 1, 0001".
- Inline `style` attributes moved to `static/css/meh.css`.
- Optional `params.footerCode` replaces the hard-coded block below the post
  list; it is HTML-escaped, so characters like `<` are kept.
- Added `theme.toml`, an `exampleSite`, screenshots, a README and this changelog.
