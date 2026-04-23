# fODE case

This folder contains the solver notebook for the fractional ordinary differential equation (fODE) case (Section 3.1 of the paper).

Unlike the 2D and 3D fPDE cases, this notebook performs both training and plotting in a single file — no separate plotter is needed.

## Files

- `fODE_solver.ipynb` — trains the fPINN model from scratch and generates the comparison figure against the analytical solution

## Problem

The notebook solves the fractional ODE:

$$\frac{\partial^{\alpha} u(t)}{\partial t^{\alpha}} = -u(t) + t^2 + \frac{8}{3\sqrt{\pi}} t^{3/2}, \quad 0 \le t \le 1, \quad \alpha = 0.5$$

with initial condition $u(0) = 0$. The analytical reference solution is $u(t) = t^2$.

The Caputo fractional derivative is discretized using the Diethelm scheme.

## Usage

```bash
jupyter notebook fODE_solver.ipynb
```

All hyperparameters (domain, collocation grid, optimizer) are defined in Section 1 of the notebook.
