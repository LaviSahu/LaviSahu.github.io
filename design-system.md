# lavisahu.github.io — Design System Brief ("Ledger")
> Personal site of Lavi Sahu. Equivalent in rigor to the Zuloma "Slow Ink" brief, deliberately
> distinct in every visible fingerprint (separation rule works both ways: no Zuloma fonts,
> colors, wordmark patterns, or links here; no personal name/photo on Zuloma).

## 1. Essence
A planner's ledger: precise, columnar, quietly confident. The canon of the best personal
.io/.dev sites — content-first, monospace-labeled, one accent, huge whitespace, zero decoration
that doesn't carry information. Name-first (real person, real photo optional), never brand-first.

Aesthetic in one line: **set, not styled** — like a well-kept ledger page, every number aligned.

## 2. Design principles (load-bearing)
1. **One column, one reading order.** Max-width 680px text column; wider (920px) only for
   tabular sections (books, travel). No sidebars, no cards-for-cards'-sake.
2. **The grid is visible only through alignment.** Hairline rules and tab-stops, never boxes.
3. **Cobalt is a signal, not a theme.** Accent only on: links-on-hover, active nav, section
   numerals, the odd data point. Never fills, never gradients.
4. **Tabular numerals everywhere numbers align** (`font-variant-numeric: tabular-nums`).
5. **Motion is a settle, not a show.** 140ms ease-out color/underline shifts; no transforms
   larger than 2px; `prefers-reduced-motion` kills transforms.

## 3. Color tokens
**Light (default)**
| Token | Value | Role |
|---|---|---|
| `--bg` | `#fafaf9` | page |
| `--surface` | `#f4f4f2` | rows-on-hover, code |
| `--ink` | `#1b1b1f` | primary text |
| `--muted` | `#6e6e76` | secondary, metadata |
| `--faint` | `#a3a3ab` | tertiary, ghost numerals |
| `--line` | `rgba(27,27,31,.09)` | hairlines |
| `--accent` | `#2247c9` | cobalt — links, active, signals |
| `--accent-ink` | `#1a3699` | accent hover/active |

**Dark (`@media prefers-color-scheme: dark` + `html[data-theme]` override)**
`--bg #101012` · `--surface #18181b` · `--ink #e9e9ec` · `--muted #94949c` ·
`--faint #5c5c64` · `--line rgba(233,233,236,.1)` · `--accent #8fa5ff` · `--accent-ink #b3c2ff`

Contrast (WCAG 2.x, computed): ink/bg 15.9:1 · muted/bg 5.6:1 · accent/bg 6.6:1 (light);
ink/bg 14.8:1 · muted/bg 5.9:1 · accent/bg 6.9:1 (dark). All AA-pass for normal text.

## 4. Typography
| Stack | Font | Use |
|---|---|---|
| `--sans` | **Inter** (400/500/600) | body, headings; `font-feature-settings:"cv11","ss03"` off — default Inter, no stylistic-set gimmicks |
| `--mono` | **IBM Plex Mono** (400/500) | labels, kickers, metadata, numerals, nav |

Scale: h1 `clamp(28px,4.5vw,44px)` sans 600 tracking `-0.022em` · section label `12px` mono
uppercase tracking `+0.14em` · body `15.5px/1.65` · meta `13px` mono · ghost numerals `13px`
mono `--faint`. No serif anywhere (Zuloma owns the serif-italic signature).

## 5. Spacing · radius · shadow
Column `680px` (text) / `920px` (tables); `--pad: clamp(20px,6vw,48px)`. Section gap
`clamp(72px,12vh,128px)`. Radius `0` everywhere except focus ring offset. Shadow: none, ever.

## 6. Components (five states where interactive)
- **Nav**: top hairline bar — name (mono, lowercase `lavi sahu`) left; section links (mono 12px)
  right; theme toggle. hover → accent; active section → accent + `text-underline-offset: 6px`
  underline; focus-visible → `2px solid var(--accent)` outline offset 2px; no disabled.
- **Section header**: ghost index (`01`, mono, `--faint`) + mono uppercase label + hairline rule
  to the right edge.
- **Ledger row** (books, travel, games, engagements list): grid `1fr auto` or
  `auto 1fr auto auto`; row link stretches; default `--ink`/`--muted`; hover: bg `--surface` +
  title → accent (140ms); active → `--accent-ink`; focus-visible outline on row.
- **Demo card** (the two live demos): full-width hairline-top block, mono kicker, title, one-line
  description, `↗` mark; same states as ledger row. External → lavisahu.pages.dev.
- **Footnote/contact links**: underline `--line` → hover underline + text accent.
- **Theme toggle**: mono glyph button (`◐`); states as nav links.

## 7. Motion
`--ease: cubic-bezier(.25,0,.1,1)`; 140ms color/border/underline; 180ms for theme cross-fade.
No parallax, no reveal-on-scroll theatrics (distinct from the old Ghibli page): content is
simply there. `prefers-reduced-motion: reduce` → transitions 0ms.

## 8. Responsive
`<640px`: nav collapses to name + toggle + horizontal-scroll section links; ledger rows stack
(title, then meta line); `--pad` floors 20px. `640–1024`: tables keep 2 columns. `>1024`: full.
Touch targets ≥44px.

## 9. Page architecture (single file, GH Pages)
`index.html`, self-contained CSS/JS, fonts via Google Fonts, system dark-mode aware + manual
toggle persisted in localStorage.

Sections: `00 hero` (name, role line, location, 2 links) · `01 work` (what I do) ·
`02 engagements` (3 anonymized cards) · `03 demos` (S&OP simulator, inventory calculator →
lavisahu.pages.dev) · `04 library` (every book, ledger rows w/ author + rating) · `05 travel`
(countries ledger + count) · `06 games` (list w/ commentary) · `07 background`
(EY, education, certifications, languages) · `08 contact` (LinkedIn, email) · footer.

## Hard rules
- No Zuloma fingerprints: no Instrument Serif/Geist/JetBrains Mono, no terracotta/cream, no
  trailing-period wordmark, no link to zuloma.com or automationdiary.
- No client names — engagement copy stays at "global FMCG major" altitude.
- No gradients, glows, shadows, glassmorphism, emoji headers, or hero portraits of code editors
  (the "AI design" tells). Photo optional and small if used.
- Numbers align. Always.
