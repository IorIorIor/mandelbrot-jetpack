# Mandelbrot Jumper

Two zero-dependency HTML toys — just open either file in a browser.

## [index.html](index.html) — the game

A charge-and-aim jumping game where the Mandelbrot set is your planet.
Gravity pulls toward the heart of the set, the camera rolls so down is
always down, and you fling a tiny blob (five billionths of the complex
plane across) around the fractal surface — collecting orbs and
slingshotting through gravity wells.

**Controls**

- **hold click / touch** — aim (toward the pointer) and charge a jump;
  release to fly
- **SPACE** — hold to charge a straight-up jump
- **← → / A D** — walk (on-screen buttons on touch devices)
- **scroll / pinch** — camera zoom (1× to 20,000,000×)
- **+ / −** — double / halve iteration depth
- **R** — reset to spawn
- **Tuning panel** — live sliders for physics, jumps, gravity wells,
  player, fractal, and camera

**Under the hood**

- Fractal rendering: GPU perturbation (float64 reference orbits plus
  per-pixel float32 deltas) baked into a lazy tile pyramid of
  iteration/distance textures — recoloring is free, steady-state frames
  composite in under a millisecond, and the analytic distance-estimate
  antialiasing stays correct at any zoom.
- Collision: a player-centered signed-distance field baked from the same
  escape-time terrain, giving exact circle contact, true surface normals,
  sliding, and static friction; an analytic DE ray-march handles high
  speeds and unbaked territory.
- Orbs and gravity wells are hash-seeded from world position — the same
  field for every player, no storage.

## [explorer.html](explorer.html)

A classic pan-and-zoom Mandelbrot explorer (Canvas 2D).

- **scroll** — zoom toward cursor
- **drag** — pan
- **+ / −** — iteration depth
- **R** — reset
