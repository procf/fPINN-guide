# Fractional Physics-Informed Neural Networks (fPINNs) with Caputo Derivatives

This repository contains the source code and trained model weights accompanying the paper:

> Dabiri, D., DaRosa, J., Saadat, M., Mangal, D., Jamali, S. *"A detailed and comprehensive account of fractional Physics-Informed Neural Networks: From implementation to efficiency."* [Journal Name, Year]. [DOI link when available]

## Overview

This project provides a systematic study of fractional physics-informed neural networks (fPINNs) for solving:

- Fractional ordinary differential equations (fODEs)
- Two-dimensional fractional partial differential equations (2D fPDEs)
- Three-dimensional fractional partial differential equations (3D fPDEs)

Two numerical discretizations of the Caputo fractional derivative are compared within a unified fPINN framework: the **Diethelm** method and the **L1** method.

## Repository structure

The repository is organized by problem dimensionality, matching the structure of the paper.

Each case folder contains:
- A **solver** notebook that trains the fPINN from scratch
- A **plotter** notebook that loads saved weights and regenerates paper figures
- A set of **pre-trained weight** folders for each configuration studied in the paper

## Requirements

- Python 3.10+
- TensorFlow 2.x (tested on 2.19)
- NumPy, Matplotlib, Pandas, openpyxl, SciPy

Install dependencies with:

```bash
pip install -r requirements.txt
```

## Usage

### Reproducing the figures

To regenerate the figures in the paper without re-training, navigate to the relevant case folder and open the plotter notebook:

```bash
cd 2D_fPDE
jupyter notebook 2DfPDE_plotter.ipynb
```

The plotter loads the pre-trained weights from the `WEIGHTS_*/` folders in the same directory and produces the comparison figures.

### Training from scratch

To train a new fPINN model, navigate to the relevant case folder and open the solver notebook:

```bash
cd 2D_fPDE
jupyter notebook 2DfPDE_solver.ipynb
```

All hyperparameters (domain, collocation grid, optimizer, stopping criteria) are defined in Section 1 of each solver notebook. Modify them and run all cells.

## Citation

If you use this code in your research, please cite:

```bibtex
@article{dabiri2024fpinn,
  title   = {A detailed and comprehensive account of fractional Physics-Informed Neural Networks: From implementation to efficiency},
  author  = {Dabiri, Donya and DaRosa, Joshua and Saadat, Milad and Mangal, Deepak and Jamali, Safa},
  journal = {Artificial Intelligence for Engineering},
  year    = {2026},
  doi     = {https://doi.org/10.1049/aie2.70024}
}
```

## License

This code is released under the MIT License. See [LICENSE](LICENSE) for details.

## Contact

For questions, please contact Donya Dabiri at dabiri.d@northeastern.edu or open an issue on GitHub.

## Acknowledgements

This work was supported by the National Science Foundation's DMREF program through Award #2118962 and Army Research Office (Grant W911NF-22-1-0172).
