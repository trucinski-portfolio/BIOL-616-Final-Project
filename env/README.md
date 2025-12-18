# Computational Environment Documentation

This directory documents the software environments used to run the analysis
pipeline in this repository. The goal is transparency and reproducibility,
not environment reconstruction via containers.

---

## Python Environment (Script 01: Preprocessing)

The preprocessing step (`scripts/01_preprocessing.ipynb`) was executed using
Python on a shared academic compute environment.

- Python version: 3.9.16
- Package manager: pip 24.2

All Python dependencies present at the time of analysis were captured using
`pip freeze` and are recorded in:

    requirements_python.txt

This file reflects the exact package versions installed on the shared compute
system at runtime.

---

## R Environment (Script 02: Differential Expression)

The differential expression analysis
(`scripts/02_differential_expression.ipynb`) was executed using:

- R version: 4.2.0 (2022-04-22)
- Platform: x86_64-conda-linux-gnu
- Operating system: Ubuntu 20.04.4 LTS
- BLAS/LAPACK: OpenBLAS (conda-provided)

Primary analysis package:
- limma (v3.54.2)

This step relies on Bioconductor and base R functionality. The environment was
not containerized; instead, key version information is documented to support
interpretation and approximate reproducibility.

---

## R Environment (Script 03: Visualization)

The visualization and downstream analysis
(`scripts/03_visualization.ipynb`) was executed using the same R installation
as Script 02:

- R version: 4.2.0 (2022-04-22)
- Platform: x86_64-conda-linux-gnu
- Operating system: Ubuntu 20.04.4 LTS

Major visualization and analysis packages include:
- ggplot2 (v4.0.1)
- ComplexHeatmap (v2.14.0)
- data.table (v1.17.8)
- cowplot (v1.2.0)
- dplyr, readr, stringr

---

## Notes on Reproducibility

- No Docker or Conda environment files are provided.
- Environments reflect the reality of execution on a shared academic server.
- Exact Python dependencies are frozen; R dependencies are documented by
  version and package name.
- The analysis is intended to be reproducible in principle, with exact
  numerical replication depending on environment parity.
