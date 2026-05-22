# Session Handoff — Website Build

Snapshot for a future Claude session to pick up where this one left off.
Written: 2026-04-20.

## Who / Where
- User: snizzzy (GitHub), es.sniperfx@gmail.com
- Repo root: `/Users/mattloeber/Website build`
- Branch: `main` (main is the PR base)
- Remote: `https://github.com/snizzzy/mattloeber`

## Project Shape
- Single-file site: [index.html](index.html), all styles inline.
- Tailwind via CDN in the HTML.
- Brand assets in [brand_assets/](brand_assets/) — currently only `Logo.jpg`. Use it; don't invent brand colors.
- Helper scripts in project root: `serve.mjs`, `screenshot.mjs`.

## Workflow (from CLAUDE.md — do not deviate)
1. Invoke the `frontend-design` skill before writing any frontend code.
2. Start server once: `node serve.mjs` → serves root at `http://localhost:3000`. Don't double-start.
3. Screenshot via `node screenshot.mjs http://localhost:3000 [label]` → saves to `temporary screenshots/screenshot-N[-label].png`.
4. Read the PNG back with the Read tool and compare against reference. Do **≥2 comparison rounds**.
5. Never screenshot a `file:///` URL.

## Design Rules (condensed — full list in CLAUDE.md)
- Reference image present → match exactly; placeholder content only (`https://placehold.co/WxH`).
- No reference → design from scratch with the anti-generic guardrails.
- **Never**: default Tailwind indigo/blue as primary, flat `shadow-md`, `transition-all`, same font for headings + body, adding sections not in the reference.
- **Always**: layered color-tinted shadows, display+sans font pairing, tight tracking on big headings, layered radial gradients + SVG grain, spring-easing on `transform`/`opacity` only, hover + focus-visible + active on every interactive element.

## Current State (uncommitted)
- `index.html` has **unstaged** mobile-responsive CSS additions inside `@media (max-width: 767px)` (~lines 225–277):
  - Tighter gaps on `.grid-2`, `.grid-3`, `.hero-grid`.
  - Nav wraps; compact font sizes.
  - Hero padding/typography reduced; hero visual banner stacks vertically with smaller logo.
  - Section paddings reduced; `.section-rounded` gets tighter margins.
  - Card padding/min-height reduced; services accordion indent reduced.
- Last commit (`2d7918f`): hero tagline/headline/CTAs centered into single column.
- Nothing on hero-centering work appears open; mobile polish is the live thread.

## Likely Next Steps
- Screenshot at mobile viewport (375px-ish) and desktop, compare, iterate.
- Decide whether to commit the mobile CSS block or keep iterating first.
- If committing, message should describe mobile responsive pass (not "fix").

## Gotchas
- CLAUDE.md references a Windows Puppeteer path (`C:/Users/nateh/...`) but this machine is macOS (`/Users/mattloeber`). `screenshot.mjs` is the source of truth — trust the script, ignore the stale path note.
- `git status` at session start showed `M index.html` — that's the mobile CSS above, not hero work.

## Persistent Memory (already auto-loaded in future sessions)
- GitHub username: snizzzy
- Email: es.sniperfx@gmail.com
- Date context: 2026-04-20
- Location: `/Users/mattloeber/.claude/projects/-Users-mattloeber-Website-build/memory/`
