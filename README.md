# Modified RETIRA Workflow

[![Python](https://img.shields.io/badge/Python-3.13-blue.svg)]()
[![License](https://img.shields.io/badge/License-MIT-green.svg)]()

## Overview

This repository contains the semi-automatic Python workflow developed for the manuscript:

> **Development of a Thermal Anomaly Detection System from Medium and Small Earthquakes using Thermal Infrared Remote Sensing Data**

The workflow implements an improved **Robust Estimator of Thermal Infrared Anomalies (RETIRA)** by incorporating **land-cover-conditioned thermal background estimation**.

Unlike the conventional RETIRA approach, the proposed workflow evaluates multiple background estimation strategies based on land-cover information to reduce background variability in heterogeneous landscapes.

The repository accompanies the journal manuscript and is provided to improve computational reproducibility.

---

# Methodology

The workflow evaluates three RETIRA background estimation strategies.

1. Conventional (Land–Water Mask)

2. Majority Land-Cover

3. Continuity Land-Cover

The corresponding methodology is described in the manuscript.

---

# Repository Structure

```
Modified_RETIRA_Workflow/

│
├── RETIRA_LW.ipynb
├── RETIRA_LC.ipynb
│
├── requirements.txt
├── LICENSE
└── README.md
```

---

# Workflow

The workflow consists of the following processing steps.

1. Import MODIS Land Surface Temperature (LST)
2. Convert digital values into physical temperature
3. Prepare annual land-cover data (MCD12Q1)
4. Prepare MODIS FIRMS hotspot observations
5. Calculate spatial mean temperature
6. Calculate ΔT
7. Estimate RETIRA
8. Apply Majority or Continuity land-cover filtering
9. Export thermal anomaly products

---

# Notebook Description

## RETIRA_LW.ipynb

Implements the conventional Land–Water background estimation workflow.

## RETIRA_LC.ipynb

Implements the proposed land-cover-conditioned workflow, including:

- Majority land-cover strategy
- Continuity land-cover strategy

---

# Required Input Data

The workflow requires the following datasets.

- MODIS Terra/Aqua Land Surface Temperature
- MCD12Q1 Land Cover
- MODIS FIRMS Active Fire
- Area of Interest (AOI)

The original datasets are publicly available from NASA and FIRMS.

They are **not included** in this repository because of data volume and redistribution policies.

---

# Software Requirements

Python 3.13

Major packages include

- NumPy
- Pandas
- Rasterio
- GeoPandas
- Rioxarray
- Xarray
- Dask
- SciPy
- OpenPyXL

Install dependencies using

```bash
pip install -r requirements.txt
```

---

# Running the Workflow

Before executing the notebooks, modify the project directory.

```python
PROJECT_DIR = Path("/your/project/path")
```

Run the notebook sequentially from top to bottom.

---

# Computational Notes

The workflow supports

- Desktop computing
- Cloud computing
- Parallel processing using Dask

Processing performance depends on

- CPU configuration
- RAM
- Storage performance
- Number of Dask workers

---

# Reproducibility

The workflow reproduces the computational procedures described in the associated manuscript.

Minor differences in execution time may occur depending on hardware configuration and Dask scheduling.

---

# Citation

If this workflow contributes to your research, please cite the associated manuscript.

Hemkaew, K., & Suwanprasit, C.

Development of a Thermal Anomaly Detection System from Medium and Small Earthquakes using Thermal Infrared Remote Sensing Data.

(Under Review)

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

Email: your_email@cmu.ac.th
