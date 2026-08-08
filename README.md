# Mandelbrot Jetpack

Two zero-dependency HTML toys — just open either file in a browser.

## [index.html](index.html) — the platformer

A tiny jetpack platformer where the Mandelbrot set is your planet. Gravity
pulls toward the heart of the set, the jetpack thrusts away from it, and the
camera rolls so down is always down. The fractal renders on the GPU with
perturbation (a float64 reference orbit plus per-pixel float32 deltas), so
it stays crisp to around 10^12× zoom; physics and collision run on the CPU
by sampling a handful of points around the player, who is five billionths
of the complex plane across.

- **← → / A D** — move (tangentially, planet-style)
- **SPACE** — jetpack (fuel drains, regenerates when idle)
- **scroll** — camera zoom
- **+ / −** — double / halve iteration depth
- **R** — reset to spawn
- **Tuning panel** — live sliders for physics, player, fractal, and camera

## [explorer.html](explorer.html)

A classic pan-and-zoom Mandelbrot explorer (Canvas 2D).

- **scroll** — zoom toward cursor
- **drag** — pan
- **+ / −** — iteration depth
- **R** — reset
