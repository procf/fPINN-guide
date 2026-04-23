# 2D fPDE case

This folder contains the solver and plotter notebooks, and pre-trained model weights, for the two-dimensional fractional PDE case (Section 3.2 of the paper).

## Files

- `2DfPDE_solver.ipynb` — trains the fPINN model from scratch using either the Diethelm or L1 Caputo discretization
- `2DfPDE_plotter.ipynb` — loads saved weights and regenerates the paper figures (collocation-point effect, time-window effect, Diethelm vs. L1 comparison)

## Pre-trained weights

Each `WEIGHTS_*/` folder contains the trained model for a specific configuration, named using the pattern `WEIGHTS_{Nt}t{Nx}x_tmax{TMAX}_{method}/`:

| Folder | N (time) | N (space) | T_max | Method |
|---|---|---|---|---|
| `WEIGHTS_10t10x_tmax1.0_cpt` | 10 | 10 | 1.0 | Diethelm |
| `WEIGHTS_10t10x_tmax1.0_L1` | 10 | 10 | 1.0 | L1 |
| `WEIGHTS_20t20x_tmax1.0_cpt` | 20 | 20 | 1.0 | Diethelm |
| `WEIGHTS_20t20x_tmax0.5_cpt` | 20 | 20 | 0.5 | Diethelm |
| `WEIGHTS_50t50x_tmax1.0_cpt` | 50 | 50 | 1.0 | Diethelm |
| `WEIGHTS_50t50x_tmax0.5_cpt` | 50 | 50 | 0.5 | Diethelm |

Note: `_cpt` refers to the Caputo (Diethelm) method.

## Reproducing the paper figures

```bash
jupyter notebook 2DfPDE_plotter.ipynb
```

Run all cells. The notebook loads the weights above and produces the corresponding figures.

## Training from scratch

```bash
jupyter notebook 2DfPDE_solver.ipynb
```

All hyperparameters (domain, collocation grid, optimizer, stopping criteria) are defined in Section 1 of the notebook.