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
