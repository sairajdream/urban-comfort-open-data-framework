# Urban Comfort from Open Environmental Data

A fully reproducible framework for estimating **urban environmental comfort potential** using **only open data**, illustrated for the London boroughs of **Camden** and **Islington**.

The project builds a venue-level composite indicator called **ComfortScore**, combining:

- Acoustic conditions (QuietScore)
- Vegetative presence (GreenScore)
- Structural crowd pressure (CrowdScore)
- A minimal accessibility signal (AccessScore)

The focus is on **reproducibility, transparency, and ethical use of data**, not on predicting individual wellbeing or using personal / behavioural data.

---

## 1. Repository structure

```text
urban-comfort-open-data-framework/
├── notebooks/
│   ├── 01_phase_A_data_acquisition.ipynb
│   ├── 02_phase_B_feature_engineering.ipynb
│   ├── 03_phase_C_comfortscore_model.ipynb
│   ├── 04_phase_D_external_validation.ipynb
│   ├── 05_phase_E_spatial_inequality.ipynb
│   └── 99_phase_master_pipeline.ipynb     # Optional merged pipeline
├── data/
│   ├── raw/          # Downloaded open datasets (not tracked in git by default)
│   └── processed/    # Derived feature tables and intermediate outputs
├── environment.yml   # Conda environment for full reproducibility
├── LICENSE           # MIT licence (code and notebooks)
└── README.md

