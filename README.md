# Urban Comfort from Open Environmental Data

A fully reproducible and explainable framework for assessing **urban environmental comfort potential** using **open environmental and spatial data only**, illustrated for the London boroughs of **Camden** and **Islington**.

The framework constructs a venue level composite indicator, **ComfortScore**, by integrating independent structural signals that influence environmental comfort:

* **Acoustic conditions** derived from strategic road noise maps (QuietScore)
* **Vegetative presence** derived from satellite based NDVI (GreenScore)
* **Structural crowd pressure** inferred from built and activity proxies (CrowdScore)
* **Basic accessibility support** derived from open infrastructure indicators (AccessScore)

The work explicitly focuses on **measurement rather than prediction**, and on **reproducibility, transparency, and ethical data use**.
No personal data, behavioural tracking, surveys, or user level inference are used at any stage.


## Scope and intent

This repository is designed to demonstrate:

* How urban environmental comfort can be **measured structurally** using open data
* How such measurements can be made **reproducible across cities and time**
* How ethical concerns associated with survey based or behavioural approaches can be avoided
* How uncertainty and limitations can be exposed rather than hidden

The framework does **not** aim to predict individual wellbeing or subjective experience.
It instead provides a defensible, auditable baseline for spatial comparison and inequality analysis.


## Repository structure

```text
urban-comfort-open-data-framework/
├── notebooks/
│   ├── 01_phase_A_data_acquisition.ipynb
│   ├── 02_phase_B_feature_engineering.ipynb
│   ├── 03_phase_C_comfortscore_model.ipynb
│   ├── 04_phase_D_external_validation.ipynb
│   ├── 05_phase_E_spatial_inequality.ipynb
│   ├── 06_phase_F_final_synthesis_and_future_directions.ipynb
│   └── 99_phase_master_pipeline.ipynb   # Single file for Phase A-F
├── figures/
│   └── *.png                            # Reproducible figure exports
├── requirements.txt
├── LICENSE
├── README.md
└── .gitignore

```

### Important note on data folders

The `data/` directory is **intentionally excluded from version control** due to file size constraints and to follow best practice.
All datasets are obtained from **public, open licence sources** and can be regenerated automatically by running the notebooks.


## Reproducibility and execution order

The project is organised as a **linear, phase based pipeline**.
Each notebook can be run independently, but the intended execution order is:

1. **Phase A**
   Data acquisition from authoritative open sources.
   Raw datasets are downloaded, cached locally, and logged with provenance metadata.

2. **Phase B**
   Feature engineering using a consistent venue centred spatial support.
   Environmental and structural features are computed and saved to processed files.

3. **Phase C**
   Construction of the ComfortScore composite and explanation layers.
   No external validation data are used at this stage.

4. **Phase D**
   External validation using independent structural proxies measured on the same spatial support.
   Rank based statistics and falsification tests are used to assess agreement.

5. **Phase E**
   Spatial inequality analysis and aggregation across neighbourhoods and boroughs.

6. **Phase master pipeline (optional)**
   A merged notebook created automatically from the individual phases for reviewers who prefer a single linear document.

Each phase writes **explicit outputs and provenance logs** that are consumed by the next phase, ensuring clean separation and auditability.


## Data availability and ethics

* All data sources are **open licence** and publicly documented
* No personal, survey, behavioural, or device level data are used
* No tracking, inference about individuals, or prediction of wellbeing is performed
* Spatial measurements are computed on venue buffers only

This design choice ensures that the framework is:

* Reproducible without consent or privacy concerns
* Portable across cities
* Suitable for academic review and policy facing contexts


## Installation

Create a virtual environment and install dependencies:

```bash
python -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

The notebooks were developed and tested on Linux, but should run on any standard Python environment with geospatial support.


## How to reproduce the results

1. Clone the repository
2. Install dependencies
3. Run notebooks in order from Phase A to Phase E

   * **Note**: In **Phase D**, cell **D1** requires a one time **manual download** of an external open dataset and placing it in the specified local path.
   * All subsequent steps in Phase D and all other phases are fully automated.
4. All required data will otherwise be downloaded or generated automatically

No manual data preparation is required.


## Licence

All code and notebooks are released under the **MIT Licence**.
Underlying datasets retain their original licences, which are cited and documented within the notebooks.


