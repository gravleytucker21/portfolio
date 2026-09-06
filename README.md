# UX Portfolio

A single-file UX design and research portfolio. No build step, no dependencies —
`index.html` is the entire site.

## Structure

Home, three case studies, and an About page, routed client-side off the URL hash:

| Path | Page |
| --- | --- |
| `#/` | Home — selected work, how I work, contact |
| `#/p/onboarding` | Case study — first-week churn |
| `#/p/medrec` | Case study — medication reconciliation |
| `#/p/designsystem` | Case study — design system adoption |
| `#/about` | About |

## Dev mode

Press `Ctrl` + `Shift` + `D` (or the **Dev** link in the footer). `Esc` closes it.

- Click any dashed text to rewrite it in place.
- The panel adjusts typefaces, text sizing, item sizing, spacing, and the accent
  colour. Everything is a CSS custom property, applied live.
- Changes auto-save to `localStorage` as a draft, so a refresh won't lose them.

To make a change permanent, use **Download** (writes a fresh `index.html`) or
**Copy HTML**, then replace this file and push. The **Publish** button only works
inside claude.ai, where the page can republish itself; on this site it is inert.

## How the page is built

Content and design tokens live in the `<script id="state" type="application/json">`
block. The page renders itself from that state — it does not contain hand-written
markup for the case studies. Export regenerates a complete document from the state
plus the page's own captured CSS and script, so the output stays clean source
rather than a DOM snapshot.

That means: **edit the JSON state, not the rendered markup.**

## Deploying

Static hosting, no configuration. No build command, no output directory —
just serve the repository root.

## Placeholder content

Every name, project, quote, and figure is a placeholder. Swap:

1. `site.name` and `site.email` in the state block
2. The three entries in `projects`
3. `[Company]`, `[Agency]`, `[Startup]` on the About page
4. Chart values — `chart.items[].value` drives the geometry; the visible
   labels are separate fields
