# Urban Comfort from Open Environmental Data

## What this repository is
Cities do not feel the same everywhere. Some places are calmer, while others are louder, busier, or more intense. This repository provides a reproducible framework to assess **urban environmental comfort potential** using **open environmental and spatial data only**.

It does not track people, use surveys, or collect personal data. Instead, it measures **place conditions**, so results are transparent, repeatable, and privacy safe.

## Non technical overview
### What ComfortScore means
ComfortScore is a **place based indicator**. It describes how supportive the physical environment is likely to be, based on measurable conditions such as:
- long-term road traffic noise exposure
- nearby vegetation
- structural activity pressure from open proxies
- basic accessibility support from open infrastructure indicators

### What ComfortScore is not
- It is **not** a prediction of individual wellbeing.
- It is **not** a medical or diagnostic tool.
- It does **not** measure personal experience directly.
- It does **not** use behavioural traces, device signals, or user tracking.

### Who this helps
- **Neurodivergent people, carers, and support workers**: to identify calmer venue options and reduce guesswork.
- **Councils, universities, and institutions**: to understand where conditions are least supportive and where improvements can be targeted fairly.

## Practical uses for councils, universities, and institutions
This framework can support:
- **Baseline mapping** of comfort potential across an area
- **Hotspot identification** where conditions are least supportive
- **Component breakdown** showing what is driving low comfort (noise, low greenery, high activity pressure, low access support)
- **Spatial inequality analysis** to compare neighbourhoods or zones using the same method
- **Evidence for planning discussions** with a transparent, auditable scoring approach

Note: this repository provides the measurement pipeline and outputs. Decisions should be combined with local knowledge and engagement.

## What the outputs look like
You can expect:
- a venue level table with ComfortScore and component scores
- maps of higher and lower comfort potential
- area aggregation for borough or neighbourhood comparison
- robustness and validation outputs (rank stability and proxy coherence)

### Example comfort map
Add an image file at `figures/comfortscore_top_bottom_10pct.png` and enable it here:

![Example comfort map](figures/comfortscore_top_bottom_10pct.png)


Caption suggestion: Example comfort map showing relative comfort potential across venues. Red indicates lower relative comfort potential and green indicates higher relative comfort potential.

## Method summary
The framework constructs a venue level composite indicator by integrating independent structural signals:

- **QuietScore** from strategic road noise mapping
- **GreenScore** from satellite derived vegetation (NDVI)
- **CrowdScore** from structural activity pressure using open proxies
- **AccessScore** from basic open accessibility indicators

These components are combined with a transparent scoring procedure to create a composite **ComfortScore**.

## Study area
The reference case study focuses on venue level assessment in inner London, illustrated for Camden and Islington.

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
│   └── 99_phase_master_pipeline.ipynb   # Single file for Phase A to Phase F
├── figures/
│   └── *.png                            # Reproducible figure exports
├── requirements.txt
├── LICENSE
├── README.md
└── .gitignore
```

### Important note on data folders

The `data/` directory is **intentionally excluded from version control** due to file size constraints and to follow best practice. All datasets are obtained from **public, open licence sources** and can be regenerated automatically by running the notebooks.

## Reproducibility and execution order

The project is organised as a **linear, phase based pipeline**. Each notebook can be run independently, but the intended execution order is:

1. **Phase A**
Data acquisition from authoritative open sources. Raw datasets are downloaded, cached locally, and logged with provenance metadata.

2. **Phase B**
Feature engineering using a consistent venue centred spatial support. Environmental and structural features are computed and saved to processed files.

3. **Phase C**
Construction of the ComfortScore composite and explanation layers. No external validation data are used at this stage.

4. **Phase D**
External validation using independent structural proxies measured on the same spatial support. Rank based statistics and falsification tests are used to assess agreement. Phase D includes one external open dataset that requires a one time manual download due to licensing or access constraints.

5. **Phase E**
Spatial inequality analysis and aggregation across neighbourhoods and boroughs.

6. **Phase master pipeline (optional)**
A merged notebook created automatically from the individual phases for reviewers who prefer a single linear document.

Each phase writes **explicit outputs and provenance logs** that are consumed by the next phase, ensuring clean separation and auditability. The notebooks were developed and tested on Linux. They should run on other systems with standard Python geospatial support.

## How to reproduce results

1. Clone the repository
2. Install dependencies
3. Run notebooks from Phase A to Phase E in order
4. Complete the one time manual download step described in Phase D
5. Export figures from the notebooks if required

## Citation

If you use this repository in academic or policy work, please cite the associated research output.

## Licence

This repository is released under **CC BY 4.0**. Please provide attribution when reusing.
For institutional deployment or procurement contexts, contact MindHaven for guidance on responsible use.

