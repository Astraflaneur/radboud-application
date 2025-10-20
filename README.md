# radboud-application

**Author:** Sagar Barad  
**Contact:** [sagar.barad@niser.ac.in]  
**Repository purpose:** Research application materials and reproducible demo for the project  
**“Representation Phase Transitions in Low-Rank Neural Networks.”**

## Overview

This repository accompanies my PhD application to the Radboud Institute for Computing and Information Sciences (Radboud AI).  
It contains:

- A 1-page proposal outlining the three-phase research program on **structure–energy–transfer interactions** in biological learning.
- A 3-page **technical appendix** (this work) demonstrating analytic and computational treatment of a concrete subproblem:  
  _how low-rank connectivity plus noise controls representation dimensionality and phase transitions_.
- A fully reproducible Python notebook and minimal script that generate all reported figures.

The project illustrates the connection between **statistical physics of random matrices** and **representation geometry** in constrained neural networks.


## epository structure

```

radboud-application/
│
├── proposal.pdf           # Main research proposal
├── technical_appendix.pdf       # 3-page technical appendix (this document)
├── demo_notebook.ipynb          # Jupyter notebook for PR(r, ε) experiment
│
├── demo/
│   ├── demo_id_vs_rank_noise.py    # Minimal reproducible Python script
│   └── fig1.png                    # Generated PR heatmap (output)
│
├── README.md                       # This file
└── requirements.txt                # Python dependencies

```

## Environment & dependencies

**Python:** 3.11+  
**Required packages:**  
```bash
numpy>=1.23
matplotlib>=3.7
````

Optional:

* `cupy` for GPU acceleration (drop-in replacement for `numpy`)
* `jupyter` to run the notebook interactively

Install everything via:

```bash
pip install -r requirements.txt
```

## Analytic background (short)

The experiment tests the **Baik–Ben Arous–Péché (BBP)** transition in low-rank plus noise ensembles.
For $W = W_0 + \varepsilon R$, with rank-r structured $W_0$ and Gaussian noise $R$,
the output covariance $C_y = \mathbb{E}[yy^\top]$ shows outlier eigenvalues
that vanish into the Marchenko–Pastur bulk beyond a critical noise scale $\varepsilon_c(r)$.
The participation ratio (PR) acts as an empirical order parameter for this transition.

<!-- ---

## 🧭 Reproducibility

| Criterion                                    | Status |
| -------------------------------------------- | ------ |
| Deterministic RNG seeds                      | ✅      |
| All parameters documented                    | ✅      |
| Notebook runs top-to-bottom without edits    | ✅      |
| Outputs match fig1.png                       | ✅      |
| CPU & GPU versions identical (CuPy fallback) | ✅      |
| <10 min runtime on laptop                    | ✅      |

For GPU or HPC runs (optional):

```bash
python demo/demo_id_vs_rank_noise.py --use-cupy --save demo/fig1_gpu.png
```

A small `Slurm` example for parallel grid sweeps is included in the comments of the script.

---

## 🧩 Next steps (PhD plan links)

This demo corresponds to **Phase A** of the proposed research:

> *Structure → geometry → phase transitions.*

Later phases (B, C) will build on this:

* **Phase B:** derive energy–accuracy trade-offs for synaptic updates.
* **Phase C:** predict architecture-aware task-similarity bounds for transfer.

--- -->

## References

1. Baik, J., Ben Arous, G., & Péché, S. (2005). *Phase transition of the largest eigenvalue for nonnull complex sample covariance matrices.*
2. Marchenko, V. A., & Pastur, L. A. (1967). *Distribution of eigenvalues for some sets of random matrices.*
3. Cunningham, J. P., & Yu, B. M. (2014). *Dimensionality reduction for large-scale neural recordings.*
4. Benna, M. K., & Fusi, S. (2016). *Computational principles of synaptic memory consolidation.* *Nat Neurosci.*
5. Attwell, D., & Laughlin, S. B. (2001). *An energy budget for signaling in grey matter of the brain.*

## License

MIT License (for code).
Figures and text © 2025 Sagar Barad, shared for academic review only.

*This repository is designed for full transparency and easy verification by reviewers, all code is deterministic, documented, and runs end-to-end on CPU or GPU.*

