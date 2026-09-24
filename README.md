# Harmonices Mundi

A music box played by gravity, after Johannes Kepler's 1619 claim that the planets sing.

Throw planets into orbit around a star. Each time one crosses a golden needle it plucks a note; closer to the star is higher, so orbits that resonate also harmonize (3:2 is a fifth, 2:1 an octave). Switch to **Sing** and every planet hums at a pitch proportional to its angular speed, which is Kepler's own method: a slide whose width depends only on the orbit's eccentricity. Earth's comes out at about a semitone, Kepler's *mi, fa, mi*.

**Play it:** https://jonnybowen.github.io/harmonices-mundi/

## Run it

It's one self-contained file. Open `index.html` in a browser, or serve the folder:

```bash
python -m http.server 8765
```

then visit http://localhost:8765. Click **Turn on sound** (browsers need a gesture before audio can play).

## Play

- **Tap** the sky to set a planet in a circular orbit. **Drag** to throw one into an ellipse; the dotted preview shows its path and the notes it will play.
- **Tap a planet** to remove it. Hover (mouse) for its note, period and eccentricity.
- **Voice**: Pluck or Sing. **Tuning**: Pure orbital ratios or A major pentatonic. **Needles**: 1–4. An ellipse crosses each needle at a different distance, so more needles turn one note into a melody.
- **Tempo** 0.25×–4× changes time, not pitch. **Space** pauses.

## Skies

| Preset | What's real |
|---|---|
| Kepler's six | Real eccentricities and orientations; distances compressed so the average notes form an A major chord |
| TRAPPIST-1 | Real periods and eccentricities of the seven planets; their near-resonant chain plays as a chord |
| Jupiter's moons | Real periods; Io, Europa and Ganymede held in the 1:2:4 Laplace resonance, Callisto free |
| Empty sky | Yours |

## How it's built

Plain HTML, CSS and JavaScript in `index.html`: two canvases, the Web Audio API, and Google Fonts. No build step, no dependencies. Planets feel only the star's gravity, integrated with an adaptive leapfrog step, so every bound orbit is closed and repeats forever.
