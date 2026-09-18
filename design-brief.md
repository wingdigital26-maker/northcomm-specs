# design-brief.md — northcomm / site
opened: 2026-09-18
judge_model: fable-5.1 (fallback: opus)   # one judge model for the whole build
builder_model: sonnet-5
budget_cap: 10 vision judgments (x3 orderings = 30 image calls), 4 rounds max

## References (Stage 1) — at least two, crossed with the brand
- **oxide.computer** (screenshot: `.visual/refs/oxide.png`). Borrow: a real annotated hardware artifact sitting in the right half of the hero (their server rack with a "FIG. 1" caption), console/terminal chrome as a UI motif (tabbed panel, monospace prompt), dark engineering mood translated to our light palette as "instrument panel" direction. Stays original: we keep light mode (hard constraint), our own orange, and a sweep-report/label diagram instead of a server photo.
- **teenage.engineering** (screenshot: `.visual/refs/teenage-engineering.png`). Borrow: chunky utilitarian condensed display type at real scale, a drawn/diagrammatic illustration standing in for a photograph, small mono captions used sparingly (not as a repeated eyebrow tic), tight nav-as-icon-grid rhythm. Stays original: no illustrated character, no multi-language sidebar; keep our real serials and RF trace, not whimsical art.
- **linear.app** (screenshot: `.visual/refs/linear.png`). Borrow: restraint and confidence in the hero (one headline, one subline, generous negative space, no eyebrow label, no trust-row clutter), a single quiet accent used sparingly. Stays original: we stay light-mode with a real right-side artifact instead of an empty dark void, and our type pairing (Plex Sans Condensed + Plex Mono) instead of a single grotesk.

## Diverge (Stage 2) — three tiles in .visual/tiles/{a,b,c}.html, one decider
decider: Jack | fable-5.1
pinned tokens:
-


### Decision (2026-09-18, decider: Fable 5.1, Jack absent; element-level pick)
- Winner: tile A "refined datasheet" layout (keeps the blueprint grid + Plex system shared with the ScanSpec app), with C's single-rule sheet border. Tile A/B/C's drawn label, barcode, "REV C", "N-type" and invented trace are REJECTED: they are fabricated data.
- Hero artifact = the REAL report: report-sample.webp (page 1 of the public NC-121484 sweep report, vendor logo strip cropped), shown as a sheet with a 1px ink rule, captioned in mono "NC-121484, page 1 of the report on file". Clicking it runs the lookup for NC-121484.
- Pinned tokens: --paper #fbfaf7, --sheet #ffffff, --ink #1f1e1c, --steel #5f5e5a, --line #d9d6cf, --signal #FF3800 (logo/glyphs only), --signal-text #c72c00, --signal-btn #d92f00, --pass #1d6b3a.
- Type: IBM Plex Sans Condensed 600/700 (display), IBM Plex Sans 400/500 (body), IBM Plex Mono 400/500 (serials, captions).
- Radius scale: 0 (sheets, inputs, buttons) / 2px (chips) / 50% (glyph dots only). Spacing base 8: 8/16/24/48/96.
- Refusals: no numbered eyebrow labels (01 / ...); no invented specs or drawings; no status/live indicator; light mode only; no em dashes; no shadows on sheets (rule only); no arrows on links.

## Pinned tokens
- --paper #fbfaf7
- --sheet #ffffff
- --ink #1f1e1c
- --steel #5f5e5a
- --line #d9d6cf
- --signal #FF3800 (logo/glyphs only)
- --signal-text #c72c00
- --signal-btn #d92f00
- --pass #1d6b3a

## Borrowed vs original
borrow:
original:

## Surface prerequisites
static folder; gate serves it locally
