# Raman Spectroscopy Consensus Spectra for Milk Authentication

Consensus ("average") Raman spectra built from authentic milk samples and used as a reference to detect adulterated milk.

## Repository structure

```
.
├── data/
├── notebooks/
│   ├── final_pipeline/
│   └── supplementary/
├── requirements.txt
└── README.md
```

## Data

All datasets share a common wavenumber grid of 402–3499 cm⁻¹ (3,098 points). Rows are wavenumbers and columns are spectra.

| File | Description |
|---|---|
| `raman_consensus_spectra_aligned_402_3499.xlsx` | Consensus spectra: Arithmetic Mean, B-spline Mean, Robust Median Centre, Geometric Median, Wasserstein Barycenter |
| `raman_valid_samples_combined_aligned_402_3499.xlsx` | 45 authentic milk spectra |
| `raman_functional_intensity_matrix_bspline_n4_aligned_402_3499.xlsx` | 38 adulterated milk spectra |
| `Eval_Preprocessed_aligned_402_3499_recalibrated.xlsx` | 12 held-out evaluation spectra |

## Notebooks

**Final pipeline**

| Notebook | Description |
|---|---|
| `raman_evaluation_dataset.ipynb` | Builds the evaluation dataset |
| `raman_intensity_matrix_functional.ipynb` | B-spline functional representation of the spectra |
| `raman_final_dataset_alignment.ipynb` | Aligns all datasets to a common grid |
| `adulterated_spectra_classification.ipynb` | Classifies adulterated spectra by distance to the consensus spectrum |
| `raman_loo_authenticity.ipynb` | Leave-one-out authenticity scoring |

**Supplementary**

| Notebook | Description |
|---|---|
| `raman_eda.ipynb` | Exploratory data analysis |
| `raman_consensus.ipynb` | Construction of the consensus spectra |
| `raman_decomposition.ipynb` | NMF and wavelet decomposition of the consensus spectra |
| `raman_qc.ipynb` | Consensus-based quality control of raw milk samples |
| `raman_valid_samples_combined.ipynb` | Builds the authentic dataset |
| `raman_adulterated_dataset.ipynb` | Builds the adulterated dataset |

## Installation

```bash
pip install -r requirements.txt
jupyter notebook
```
