# Northcomm Spec Lookup

Standalone public spec-sheet lookup for Northcomm RF cable test reports. Reads the live Supabase catalogue; no sign-in.

Live: https://wingdigital26-maker.github.io/northcomm-specs/

## Hard design constraints (do not break)

- **No browse / list of all reports.** A report is reachable ONLY by entering its exact serial. The lookup queries the catalogue filtered by the typed number (serial ilike) and never downloads or displays the full list. Do not re-add a browse/directory of files, and do not print a real serial as an on-page example.
- **No scroll-jank effects.** No `backdrop-filter`/`blur()` on the sticky header (repaints every scroll frame). Keep the header background solid.
- **No status / "live" / connection indicator anywhere** — no green dot, no "Catalogue online" badge, no uptime pill. Jack removed this and does not want it re-added, ever.
- Light mode only. No dark palette, no theme toggle.
- Fully separate from the scanner app. No links to the app's index.html, "installer app", or ScanSpec.
- Brand: signal orange #FF3800 for the logo, badge fills and non-text glyphs; darker orange (#c72c00 / #d92f00) for orange **text** so it meets WCAG AA. Ink and greys already pass AA.
- No em dashes in any copy.
- Show only real catalogue data with honest empty / not-found states. Never fabricate serials or numbers.
