# Pool Wind Sun — Generative Art

> A seed-based generative system for wave-simulation compositions.  
> A reproducible catalogue of computational interference studies.

---

## What is this?

**Pool Wind Sun** is a generative design system built on the 2D wave equation — the classical model of ripples on a still surface. One or several oscillating sources strike a rectangular pool; the resulting waves reflect off the boundaries and interfere with one another, producing a complex field of constructive and destructive nodes.

Every artwork in this catalogue is defined by a single numeric seed. The same seed always produces the identical composition — making each piece **traceable, reproducible, and licensable** across textile, print, and apparel applications.

Named for the three conditions that shape a ripple — the *pool* that holds it, the *wind* that stirs it, and the *sun* that lights it — **Pool Wind Sun** reframes wave interference as a textile.

---

## Live

🌐 **[View the catalogue →](https://reyrove.github.io/Pool-Wind-Sun/)**

---

## The System

The generator combines two layers:

| Layer | Description |
|-------|-------------|
| **Wave field** | A 2D wave equation stepped forward 30–70 times across a grid of 350–400 columns. |
| **Oscillators** | One or more seeded sources that inject oscillating values into the field, producing ripples that interfere. |

Both layers are driven by the same seed, ensuring deterministic output.

### Parameters

- **Grid columns** — 350 to 400
- **Grid rows** — derived from columns (offset by −10 to +10)
- **Oscillators** — `random × 0.002 × cols × rows + 1`
- **Wave speed** — `w / 200` to `w / 80`, seeded
- **Time step** — 0.04 to 0.06
- **Simulation length** — 30 to 70 iterations
- **Scale factor** — 0.75 to 1.00 (the pool fills most of the canvas)
- **Background tone** — 30 to 230 in RGB
- **Palette** — a diagonal gradient from deep blue to bright cyan, with a highlight for high-energy cells

---

## Structure

```
Pool-Wind-Sun/
├── index.html              ← Full catalogue (single-file)
├── images/
│   ├── fav.svg
│   ├── pool-tote.png
│   ├── pool-cushion.png
│   └── ...
├── Pool-Wind-Sun.jpg       ← Apparel mockup
└── README.md
```

The entire project is contained in a single `index.html` — no build step, no dependencies, no framework. Open it in any modern browser.

---

## Features

- **Seed-based generation** — every composition is deterministic and reproducible
- **Live catalogue** — cover, statement, plate, surfaces, process, archive, commission sections
- **Multiple surfaces** — print, scarf, textile, wallpaper — all rendered from the same seed
- **Archive of 8 seeds** — click any plate to load it into the main view
- **PNG export** — download any composition directly from the browser
- **Keyboard shortcuts** — `R` for new seed, `S` to save
- **Legal modal** — licensing, terms, and credits built in
- **Responsive** — works on desktop, tablet, and mobile
- **Mobile-first navbar** — horizontally scrollable with fade hint
- **Fast load** — master offscreen rendering + cached thumbnail simulations

---

## Usage

### Generate a new composition

Click **New Seed** or press `R`.

### Download the current composition

Click **Download** or press `S`.

### Load a seed from the archive

Click any plate in the **Archive** section.

---

## Color System

Every composition uses a seeded diagonal gradient that sweeps from the upper-left to the lower-right of the grid:

| Direction | Colour shift |
|-----------|--------------|
| **Vertical** (top → bottom) | Red channel rises from 10 to 50; green channel falls from 255 to 180 |
| **Horizontal** (left → right) | Blue channel rises from 200 to 255 |
| **High-energy cells** | All channels brighten by 30% toward white |
| **Opacity** | Alpha scales from 100 to 255 with wave amplitude |

The result is a field that reads as both fluid and luminous — a pool whose colours shift with the shape of the wave.

---

## Technical Notes

- Pure vanilla JavaScript — no libraries
- Canvas 2D rendering
- Custom xorshift random generator for deterministic seeds
- Device-pixel-ratio aware rendering
- Fully static rendering — one seed produces one composition, no animation loops
- **Master offscreen rendering** — the wave field is simulated once at 1024² and rendered into a master canvas; the cover, framed print, and all four surfaces blit from it
- **Archive thumbnails** — simulated at 320² with a proportionally smaller grid, then cached
- 2D wave equation with reflective boundaries at all four edges
- Oscillating source injection at seeded positions
- `prefers-reduced-motion` respected

---

## About

**Pool Wind Sun** is a project by [Reyhaneh Daneshdoost](https://reyrove.github.io/) — an Iranian-born artist working at the intersection of classical textile logic and generative systems.

The work begins with a simple observation: the woven surface — repetitive, mathematically structured, infinitely variable — has always been a form of computation, long before computers.

**Pool Wind Sun** is an attempt to render that logic visible.

> *A still pool remembers every drop that fell into it.*

---

## Licensing

All compositions are seed-documented and available for licensing across textile, surface, and apparel applications.

For commercial use, custom editions, or exclusive rights:

📧 **reyhanehdaneshdoost@gmail.com**

See the **Licensing** section in the live catalogue for details.

---

## Links

- 🌐 [Website](https://reyrove.github.io/)
- 📷 [Instagram](https://www.instagram.com/rey._.rove/)
- 💼 [LinkedIn](https://www.linkedin.com/in/reyhaneh-daneshdoost-730481160/)
- 🐦 [X](https://x.com/reyrove)

---

## Credits

**Design & Generative System**  
Reyhaneh Daneshdoost

**Typefaces**  
Cormorant Garamond · DM Mono

**Edition**  
Pool Wind Sun — Autumn 2026

---

<p align="center">
  <em>Generative Wave Simulation</em><br />
  <sub>© Reyrove Studio · All compositions reproducible by seed</sub>
</p>