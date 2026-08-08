# Mandelbrot Jetpack

Two zero-dependency HTML toys — just open either file in a browser.

## [platformer.html](platformer.html)

A tiny jetpack platformer where the Mandelbrot set is the level. The fractal
renders on the GPU (WebGL2 fragment shader, ~0.2 ms/frame at 16 iterations);
physics and collision run on the CPU by sampling a handful of points around
the player.

- **← → / A D** — move
- **SPACE** — jetpack (fuel drains, regenerates when idle)
- **scroll** — camera zoom
- **+ / −** — double / halve iteration depth
- **R** — reset

## [explorer.html](explorer.html)

A classic pan-and-zoom Mandelbrot explorer (Canvas 2D).

- **scroll** — zoom toward cursor
- **drag** — pan
- **+ / −** — iteration depth
- **R** — reset
