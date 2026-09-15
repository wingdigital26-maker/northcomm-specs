# jaswarm changelog — northcomm-specs

Permanent paper trail of the /jaswarm loop. Newest at the bottom. Commits land on branch ja/loop (not deployed until Jack merges to master).

## Round 1 — 2026-09-14 (763ad7a)
| Lane | Change | Proof |
|---|---|---|
| perf | dropped 214KB supabase-js for plain fetch() | page load ~229KB -> ~24KB |
| correctness | fixed duplicate id=browse wiping the browse header/count on load (inner list -> id=browseList) | header + "4 reports" persist |
| perf/ux | numeric browse sort (NC-121483 leads NC - 121484) | order 483/484/488/492 |
| content | privacy/support actually load IBM Plex + gained the shared top bar/footer | desktop + 375px match |
| safety | clean | — |

## Round 2 — 2026-09-14 (6e7696f)
| Lane | Change | Proof |
|---|---|---|
| perf | trimmed 3 unused font weights (Sans 500/700, Cond 600); deleted dead vendor-supabase.min.js (214KB); removed 2 dead CSS rules | correct faces load; file gone |
| visual | no changes needed | — |
| safety | clean | — |

## Round 3 — 2026-09-14
| Lane | Change | Proof |
|---|---|---|
| visual | PDF viewer loading overlay (spinner + "Loading report") while the ~7MB scan loads; hides on iframe load, 15s fallback | overlay present w/ spinner, hides on load |
| perf | no changes needed | 2 fetches negligible at 4 rows |
| practicality | no changes needed | all actions reachable, no dead ends |
| safety | clean | additive CSS/JS only |

## Round 4 — 2026-09-15 09:30
| Lane | Change | Proof |
|---|---|---|
| content | Added robots.txt + sitemap.xml (3 real pages, lastmod 2026-09-15) + branded 404.html (mirrors privacy.html chrome/tokens/fonts) | all serve 200; sitemap XML valid; 404 renders w/ real logo + Plex fonts, no console errors |
| fix | 404.html refs made root-absolute (/northcomm-specs/...) — Pages serves 404 at any depth, relative refs would break | verified at real subpath mount: logo + links load 200 |
| safety | clean — no secrets, no query-string reflection/XSS in 404, links internal/legit | gate agent: "no issues found" |
Committed: 6c81564, 2548f66 · Gap closed: SEO crawlability + off-brand default 404. Next: fine-detail pass (a11y focus states, meta completeness) or DIALED.

## Round 5 — 2026-09-15 09:36
| Lane | Change | Proof |
|---|---|---|
| a11y | :focus-visible ring (brand --signal) on all interactive elements — none existed before; @media prefers-reduced-motion stops spinner+smooth-scroll; serial input gets autocapitalize=characters/autocomplete=off/enterkeyhint=search | diff +11 lines additive; all JS ids (#q #result #searchForm #goBtn) intact, zero renames |
| safety | clean — CSS + static attributes only, no secrets/injection/new endpoints | reasoned inline (trivial surface) |
| regression | JS handlers untouched; live app renders, no console errors; lookup form + Enter-submit intact | ids grep 4/4 present |
Committed: 76ea9bc · Note: verifier agent stalled (watchdog), diff re-checked directly. Browse feature was removed in a8d9bc2 (exact-serial only now). Site is now near DIALED — SEO files, 404, a11y all done.

## Round 6 — 2026-09-15 10:38
| Lane | Change | Proof |
|---|---|---|
| content | privacy+support: removed noindex (conflicted with round-4 sitemap), added self-canonical + accurate description + theme-color + apple-touch-icon; trimmed their font imports to index.html's leaner set | diff +10 lines; both serve 200 |
| fix | corrected support description that advertised a "browse" feature the app no longer has (exact-serial only) | grep: browse absent from body, index.html L235 confirms serial-only |
| safety | clean — meta/link tags only | inline (no security surface) |
Committed: edbf520 · SITE DIALED: SEO files, branded 404, full a11y, and consistent indexable meta across all 3 pages all shipped. ja/loop 6 commits ahead of master, ready to merge -> auto-deploys via Pages.
