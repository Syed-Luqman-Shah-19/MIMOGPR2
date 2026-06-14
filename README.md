
# Improved GPR-Based CSI Acquisition via Spatial-Correlation Kernel

[![arXiv](https://img.shields.io/badge/arXiv-2601.14759-b31b1b.svg)](https://doi.org/10.48550/arXiv.2601.14759)
[![Venue](https://img.shields.io/badge/Published%20In-IEEE%20WCL-blue)](https://ieeexplore.ieee.org/)

This repository provides the Python implementation and simulation framework for the paper: **"Improved GPR-Based CSI Acquisition via Spatial-Correlation Kernel"**, accepted in *IEEE Wireless Communications Letters*.

## 📖 Abstract
Accurate channel estimation with low pilot overhead and computational complexity is key to efficiently utilizing multi-antenna wireless systems. Motivated by the evolution from purely statistical descriptions toward physics- and geometry-aware propagation models, this work focuses on incorporating channel information into a Gaussian process regression (GPR) framework for improving the channel estimation accuracy. In this work, we propose a GPR-based channel estimation framework along with a novel _Spatial-Correlation_ (SC) kernel that explicitly captures the channel's second-order statistics. We derive a closed-form expression of the proposed SC-based GPR estimator and prove that its posterior mean is optimal in terms of linear minimum mean-square error (LMMSE) under the same second-order statistics, without requiring the underlying channel distribution to be Gaussian. Our analysis reveals that, even with a $50\%$ pilot overhead reduction, the proposed method achieves the lowest normalized mean-square error, competitive empirical $95\%$ credible-interval coverage, and superior preservation of spectral efficiency compared to benchmark estimators, while maintaining lower computational complexity than the conventional LMMSE estimator.

## 🚀 Key Features
- **Spatial-Correlation Kernel:** A GPR kernel designed specifically for MIMO channel statistics.
- **MIMO Channel Simulation:** Implementations of Kronecker and Weichselberger models for realistic channel synthesis.
- **Flexible Pilot Subsampling:** Supports multiple overhead reduction cases (e.g., 25%, 33%, and 50% pilot overhead).
- **Performance Benchmarking:** Comparative analysis against RBF, Matern, and Rational Quadratic kernels, as well as LS and MMSE baselines.
- **Uncertainty Quantification:** Calculation of 95% confidence ellipses and joint coverage reliability.

## 🛠 Methodology

### Pilot Sampling Strategies
We evaluate the system under three distinct column-subsampling patterns to test robustness against overhead reduction:
- **Case I ($\Delta=2$):** 50% pilot overhead (every 2nd column sampled).
- **Case II ($\Delta=3$):** 33% pilot overhead (every 3rd column sampled).
- **Case III ($\Delta=4$):** 25% pilot overhead (every 4th column sampled).

### Evaluation Metrics
1.  **NMSE (dB):** Measures the precision of the reconstructed channel matrix.
2.  **95% Confidence Coverage:** Assesses the statistical reliability of the GPR's predicted uncertainty.
3.  **Spectral Efficiency (SE):** Evaluates the average sum-rate (bits/s/Hz) using an LMMSE detector across a range of SNR values (-10 dB to 10 dB).

## 📂 Repository Structure
- `Letter_250.h5`: The generated dataset containing channel realizations and GPR predictions (reproducible via the notebook).
- `Complex_Error_*.pdf/svg`: Visualization of real vs. imaginary error distributions.
- `NMSE_Comparison_*.pdf`: Bar charts comparing reconstruction accuracy across kernels.
- `Joint_Coverage_*.pdf`: Statistical coverage reliability plots.
- `SE_LMMSE_all.pdf`: Final communication performance comparison.

## 💻 Getting Started

### Prerequisites
- Python 3.8+
- NumPy, Scipy, Matplotlib, Seaborn
- Scikit-learn (for GPR implementations)
- H5py (for data management)

### Execution
1. Open the provided Jupyter Notebook in **Google Colab** or a local Jupyter environment.
2. Run the **Data Generation** section to create `Letter_250.h5`.
3. Run subsequent cells to generate the analytical plots used in the paper.

## 🎓 Citation
If you use this code or our Spatial-Correlation kernel in your research, please cite our paper:

```bibtex
@ARTICLE{GPR_CSI_WCL2026,
  author={Your Name and Co-authors},
  journal={IEEE Wireless Communications Letters},
  title={{Improved GPR-Based CSI Acquisition via Spatial-Correlation Kernel}},
  year={2026},
  volume={XX},
  number={YY},
  pages={ZZZ-AAA},
  doi={10.48550/arXiv.2601.14759}
}
```

## 📫 Contact
For questions regarding the implementation or the paper, please reach out to:
- **[Your Name]** - [Your Email Address]
