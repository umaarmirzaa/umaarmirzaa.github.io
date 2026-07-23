# Portfolio — Muhammad Umar Mirza

Personal portfolio. Single self-contained `index.html` — a hand-rolled pixel/graph
engine over a dark terminal UI. **Void & Synapse** theme: near-black `#0a0a0a`, no
brand hue (accent is just brighter text, `#ededef` → `#fff`), Inter body + JetBrains
Mono for data/labels.

**Sections:** whoami · projects · skills · experience · reading · let's connect

## Highlights

- **Synapse graph background** — dithered value-noise pixel field (FBM + 4×4 Bayer,
  vanilla Canvas 2D port of the React Bits PixelBlast concept) with a subset of cells
  promoted to graph nodes: nearest-neighbour edges, data-pulses flowing along them.
  - **Cursor movement** spawns small, tight graph-connection webs that trail the pointer.
  - **Clicks** fire a wide connection wave — links grow node-to-node outward, Obsidian-graph
    style, then fade.
- **Obsidian-style portrait build** — my photo as 1,380 precomputed points
  (`portrait-dots.js`). On first view the nodes pop in center-out, then edges knit in one
  by one until the face resolves, then freezes (no forever-loop).
- **Floating pill nav** — rounded glass pill that retracts on scroll down and drops back
  on scroll up. Per-link GooeyNav hover (React Bits motion, ported to pure CSS — no gsap,
  no React). On mobile the links become a horizontal scroll row.
- **Social dock** — footer pill with GitHub · X · LinkedIn · Email, spring hover.
- **Terminal UI** — typing effects, decrypt-scramble headings, split-flap stat counters,
  and a ⌘K command palette (keyboard) for jumping between sections.

No build step, no dependencies. Everything (CSS + JS) is inline except the generated
`portrait-dots.js` data file and an inline-SVG favicon.

## Launch video

`brag-output/` holds a 20s launch video (`brag.mp4`, poster `brag.jpg`, share copy)
built with [Hyperframes](https://hyperframes.heygen.com) — the centerpiece scene
re-assembles the portrait from the same 1,380-point data. Plan + composition brief are
alongside; the render scratch (`composition/`) is gitignored (third-party music, license
unverified — don't reuse without clearing it).

## Run

`serve.js` is a tiny zero-dep static server (honors `$PORT`, defaults to 4321):

```
node serve.js
```

Or any static server from the project root, e.g. `python -m http.server 8731`. Opening
`index.html` directly works too.

## UI credits / references

- [React Bits](https://reactbits.dev) — PixelBlast (background concept) and GooeyNav
  (nav hover motion); both re-implemented in vanilla Canvas/CSS, not imported.
- Obsidian graph view — portrait + click-wave animation reference.
- `ui-components/` (gitignored) — local stash of saved reference components.

## Stack

Vanilla HTML / CSS / JS · Canvas 2D · zero frameworks.
