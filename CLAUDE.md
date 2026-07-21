# AI Study Guide — project notes

Single deliverable: `index.html` — a self-contained HTML/CSS/JS study guide
(no build step, no external requests). It is bilingual EN / PT-BR via `data-pt`
attributes, and behaves as an SPA with numbered `<section>`s wired into the
sidebar nav and the home menu.

## Data sourcing (required)

**Never invent data.** Every factual figure in the guide — model prices, context
windows, benchmark scores, capability/index rankings, parameter counts, release
dates — must come from an established, citable source, not from an estimate or a
guess.

- **Pricing:** use each provider's official pricing/list page.
- **Benchmarks & capability rankings (intelligence, coding, agentic, tool use):**
  use established leaderboards — primarily
  [Artificial Analysis](https://artificialanalysis.ai/) (Intelligence Index,
  Coding Index, Agentic Index) — and cite the source and date in the chart caption.
- **Model facts** (architecture, context window, modalities, launch date): use the
  lab's own announcement / model card.
- If real numbers cannot be retrieved, **do not fabricate or label something an
  "estimate" and ship it.** Leave it out, or show a clearly-marked
  "sourcing in progress" placeholder, and flag it to the user — never present
  invented values as data.

When adding or changing any chart or table, put the source and date in the caption
so the number is traceable.

## Editing conventions

- Keep every user-facing string bilingual: the visible text is English; the
  `data-pt` attribute holds the PT-BR translation (quotes encoded as `&quot;`).
- Section headings carry a number in `<span class="num">NN</span>` (both the
  visible tag and the `data-pt` copy); the sidebar nav, home menu, and topic-count
  badge must stay in sync when sections are added, removed, or reordered.
- Verify changes in a real browser (Chromium via Playwright) before committing —
  check that charts render, the sortable table sorts, the quiz grades, and there
  are no console errors, on both desktop and mobile and in EN + PT.
