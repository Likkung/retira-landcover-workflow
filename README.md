# Modified RETIRA: Land-Cover-Conditioned Thermal Anomaly Workflow

## Overview

This repository contains the semi-automatic Python workflow developed for the study:

> **Development of a Thermal Anomaly Detection System from Medium and Small Earthquakes using Thermal Infrared Remote Sensing Data**

The workflow implements an improved RETIRA (Robust Estimator of Thermal Infrared Anomalies) processing framework by incorporating land-cover information into thermal background estimation.

The implementation supports three background estimation strategies:

- Conventional (Land–Water Mask)
- Majority Land-Cover
- Continuity Land-Cover

The repository accompanies the corresponding journal manuscript and is intended to improve the reproducibility of the proposed methodology.

---

# Repository Structure

```
Modified_TA
│
├── Thesis_Revision_LW.ipynb
├── Thesis_Revision_LC.ipynb
├── Thesis_Revision_LW_62.ipynb
├── Thesis_Revision_LC_62.ipynb
│
├── requirements.txt
├── LICENSE
└── README.md
```

---

# Workflow

The workflow consists of the following processing steps:

1. Import MODIS Land Surface Temperature (LST)
2. Convert digital values into physical temperature
3. Prepare annual land-cover maps (MCD12Q1)
4. Prepare MODIS FIRMS hotspot observations
5. Calculate spatial mean temperature (T(t))
6. Compute ΔT
7. Estimate RETIRA
8. Apply Majority or Continuity background estimation
9. Export thermal anomaly products

---

# Notebook Description

| Notebook | Description |
|------------|-------------|
| Thesis_Revision_LW.ipynb | Magnitude 4.7 earthquake using conventional land–water masking |
| Thesis_Revision_LC.ipynb | Magnitude 4.7 earthquake using land-cover-based background estimation |
| Thesis_Revision_LW_62.ipynb | Magnitude 6.2 earthquake using conventional land–water masking |
| Thesis_Revision_LC_62.ipynb | Magnitude 6.2 earthquake using land-cover-based background estimation |

---

# Input Data

The workflow requires the following datasets:

- MODIS Terra/Aqua Land Surface Temperature
- MCD12Q1 Land Cover
- MODIS FIRMS Active Fire
- Study Area Boundary (AOI)

The original datasets can be obtained from:

- NASA LP DAAC
- FIRMS
- USGS

Due to licensing and data volume, the original datasets are **not included** in this repository.

---

# Software Environment

The workflow was developed using

- Python 3.13
- Rasterio
- GeoPandas
- NumPy
- Pandas
- SciPy
- Dask
- Xarray
- Rioxarray

See `requirements.txt` for package versions.

---

# Running the Workflow

Before executing the notebooks, modify the project directory:

```python
PROJECT_DIR = Path("/your/project/path")
```

Then execute the notebook from top to bottom.

---

# Computational Notes

The workflow supports

- Desktop Computing
- High-memory Workstations
- Cloud Computing

Dask is used to distribute raster processing tasks across multiple workers.

---

# Reproducibility

The workflow implements the methodology described in the associated manuscript.

Results may vary depending on

- available RAM
- CPU configuration
- storage performance
- Dask worker configuration

---

# Citation

If you use this workflow, please cite:

Hemkaew, K., & Suwanprasit, C.

Development of a Thermal Anomaly Detection System from Medium and Small Earthquakes using Thermal Infrared Remote Sensing Data.

(under review)

---

# License

MIT License

---

# Contact

Kolik Hemkaew

Department of Geography

Faculty of Social Sciences

Chiang Mai University

Thailand

Email:
kolik_hemkaew@outlook.com
