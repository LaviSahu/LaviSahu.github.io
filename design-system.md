# lavisahu.github.io — Design System Brief ("The Planning Board")
> v2, shipped 2026-07-12 (v1 "Ledger" was rejected as too bare). Equivalent in rigor to the
> Zuloma "Slow Ink" brief; zero shared fingerprints (separation rule works both ways).

## Essence
The visual language of a planner's own artifacts: a graph-paper planning board, manifest stamps,
and a live route map. The one aesthetic risk is spent in the hero — a canvas that draws Lavi's
real flight routes (Bangalore home node → 23 cities, true lon/lat, equirectangular projection,
animated draw on load, reduced-motion safe, redrawn on theme change). Everything else is precise
and quiet. Personality carrier: massive condensed uppercase display type.

## Tokens
Light: paper #f4f5f2 (cool green-bias) · card #fbfcfa · ink #171a17 · muted #5f6660 ·
faint #9aa19a · gridline rgba(23,26,23,.055) · rule rgba(23,26,23,.14) · signal #e04f16
(logistics/container orange) · signal-soft rgba(224,79,22,.09)
Dark: paper #141613 · card #1b1e1a · ink #e9ebe4 · muted #9ba398 · faint #5e665d · signal #ff7a45
Theme: prefers-color-scheme + html[data-theme] override (token-level), toggle persists localStorage.
Ground: body carries a 56px graph-paper grid via two linear-gradients on --gridline.

## Type
- Display: **Archivo variable** (wdth 62..125, wght 300..900) — H1/H2/footline set uppercase,
  wdth ~72–80, wght 700–800, tracking −.02…−.028em. Industrial-manifest voice.
- Prose: **Source Serif 4** — travel essays and the orange book "takes" (italic).
- Data: **Spline Sans Mono** — nav, kickers, metadata, stamps, tabular-nums everywhere.

## Components
- Stamp chip (hero coordinates, mono uppercase, signal border) · sec-h with black stamped CODE
  chip (WRK/ENG/DMO/LIB/TRV/GMS/BKG/CTC) + rule · manifest stats strip (bordered grid, big
  condensed numerals, orange sup unit) · tiles (card, hover −3px lift + signal border + soft
  shadow) · dossiers (signal left spine) · proof blocks (signal-soft fill, 40px numerals) ·
  consoles (demo cards, pill badge Live/Beta, mono "go" line) · library shelf (sticky category
  rail 180px + ledger rows, serif-italic orange takes) · fieldnotes (details cards, serif essays,
  open → signal border) · spec sheet (BKG) · footer CTA buttons (primary = signal fill).
- Reveal: .rv fade-rise, gated behind html.js added ONLY when tab visible at load (hidden tabs
  never start CSS transitions — content must never depend on them). Reduced-motion: no transforms.

## Rules
No Zuloma fingerprints (no Instrument Serif/Geist/JetBrains Mono, no terracotta/cream, no
trailing-period wordmark). No client names. Signal orange is a signal, not a theme. Numbers
align (tabular-nums). Section codes are manifest codes, not fake sequence numbers.

## Files
Live: LaviSahu/lavisahu.github.io index.html (+ this brief as /design-system.md).
Mirror: gnik1487/lavisahu.github.io. Book rows generated from
Documents/Aiwork/scm-portfolio/public/books.json — regenerate on shelf changes.
