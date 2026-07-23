# Random-Walk-Simulation

Interactive Monte Carlo simulation of random walks in 1, 2, and 3 dimensions.
Everything runs client-side in a single self-contained HTML file — no server,
build step, or dependencies.

## Usage

Open `index.html` in any browser:

```bash
open index.html
```

## Features

Three tabs, one per dimension:

- **1-D walk** — position vs. step number, with each walk as its own line and
  the ensemble mean overlaid.
- **2-D walk** — walks on the x/y plane (up/down/left/right), equal axis
  scaling, origin crosshair, and the mean-position trail.
- **3-D walk** — walks on a lattice with six directions (up/down/left/right/
  forward/back), rendered in perspective. **Drag to rotate, scroll to zoom.**

Each tab has:

- **Parameters** — per-direction probabilities (any leftover below 100% is the
  chance of staying put), number of steps (up to 20,000), and number of
  simultaneous simulations (up to 5,000). Edits re-run automatically; the
  Re-run button resamples with the same settings.
- **Step-by-step playback** — the chart starts empty at step 0. Play/Pause,
  +1 step, Reset, a log-scale speed slider (1–2,000 steps/s), and a scrubber
  to jump to any step. Axes grow with the walks' footprint as playback
  advances.
- **Per-walk colors** — every simulation gets its own hue (golden-angle
  spacing), with the ensemble mean drawn on top in orange.
- **Stats** — mean and RMS/std of the final position or distance, the
  theoretical value for comparison, and the farthest excursion from origin.
- **Hover tooltips** (1-D and 2-D) and a collapsible **table view** of
  per-step ensemble statistics.

Light and dark mode follow the OS setting.

## Notes

- Statistics are computed over **all** simulations; only the first few hundred
  walks are drawn to keep rendering fast.
- Theory tiles: 1-D expected final position is `n·(p_up − p_down)`; 2-D/3-D
  RMS distance is `√(Σ_axis n·var + (n·drift)²)`.
