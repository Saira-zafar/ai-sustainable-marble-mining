# AI-Driven Sustainable Marble Mining

> An integrated AI + geospatial system for detecting, forecasting, and mitigating marble mining waste in Khyber Pakhtunkhwa, Pakistan — combining satellite imagery, GIS, deep learning, and optimization to support sustainable extraction.

[![Status](https://img.shields.io/badge/status-in%20progress-yellow)](#)
[![Python](https://img.shields.io/badge/python-3.10%2B-blue)](#)

---

## Table of Contents

- [Overview](#overview)
- [Problem Statement](#problem-statement)
- [Proposed Solution](#proposed-solution)
- [System Architecture](#system-architecture)
- [Methodology](#methodology)
- [Tech Stack](#tech-stack)
- [Project Scope](#project-scope)
- [Repository Structure](#repository-structure)
- [Getting Started](#getting-started)
- [Timeline](#timeline)
- [Team](#team)
- [References](#references)

---

## Overview

Marble mining and processing in districts such as **Buner, Swat, and Mohmand** generate large volumes of non-biodegradable slurry and powder waste. Left unmanaged, this waste blocks access to deeper marble reserves and threatens surrounding land and water ecosystems.

This project builds a **satellite-supported, AI-enabled geospatial system** that:

1. Automatically maps existing waste hotspots from multispectral satellite imagery.
2. Forecasts future waste accumulation using spatio-temporal machine learning.
3. Recommends optimized, location-specific drilling and blasting parameters to reduce waste generation and drilling time.

The goal is to shift marble mining from **reactive waste management to proactive, data-driven sustainability planning**.

## Problem Statement

Marble mining in KP suffers from unmanaged slurry disposal, inefficient drilling/blasting, and a lack of real-time monitoring or forecasting. Manual tracking cannot keep pace with the scale of waste generated, leading to lost recoverable marble, environmental contamination, and higher operating costs. There is currently no predictive system in place to anticipate waste buildup before it becomes a operational or ecological problem.

## Proposed Solution

An integrated pipeline that combines:

- **GIS & remote sensing** for spatial waste mapping and terrain analysis.
- **Deep learning segmentation** (CNN/U-Net/SegFormer) to detect waste zones from satellite imagery.
- **LSTM-based spatio-temporal forecasting** to predict future waste accumulation and risk hotspots.
- **Optimized ANN (Genetic Algorithm + Pattern Search)** to recommend drilling/blasting parameters that minimize waste and cycle time under safety constraints.
- **Explainable AI (SHAP)** to make model recommendations transparent and trustworthy for stakeholders.
- **A decision-support dashboard** with hotspot maps, forecasts, and downloadable reports.

## System Architecture

```
Field Surveys + Satellite Imagery (Sentinel-2, Landsat-8, DEMs)
                │
                ▼
     GIS-Based Topographic & Environmental Mapping
                │
                ▼
   AI Segmentation (CNN / U-Net / SegFormer) → Waste Zone Detection
                │
                ▼
     LSTM Spatio-Temporal Forecasting → Risk / Hotspot Maps
                │
                ▼
   GA-PS Optimized ANN → Drilling & Blasting Recommendations
                │
                ▼
     SHAP Explainability + Field Validation
                │
                ▼
        Decision Support Dashboard (Web)
```

## Methodology

| Phase | Description |
|---|---|
| **1. Data Gathering & Preparation** | Field surveys (Buner, Mohmand, Swat), DEM acquisition (SRTM/ASTER), multispectral imagery (Sentinel-2, Landsat-8), georeferencing & preprocessing. |
| **2. Topographic & Environmental Mapping (GIS)** | Derive elevation, slope, aspect, drainage, and land-use/land-cover (LULC) maps as model features. |
| **3. Waste Detection (AI Segmentation)** | Train CNN/U-Net and SegFormer on labeled satellite tiles with field-validated masks. |
| **4. Forecasting (Spatio-Temporal Analysis)** | LSTM and hybrid models forecast waste accumulation; generate probabilistic risk maps. |
| **5. Drilling & Blasting Optimization** | ANN optimized via Genetic Algorithm + Pattern Search recommends parameters minimizing waste/cycle time under safety constraints. |
| **6. Validation & Explainability** | SHAP-based interpretation; validation via segmentation accuracy, RMSE, and drilling efficiency gains. |
| **7. Decision Support & Visualization** | Web dashboard with forecasts, hotspot maps, optimized recommendations, and downloadable reports. |

## Tech Stack

**Geospatial & Data**
- ArcGIS Pro, Google Earth Engine
- Sentinel-1/2, Landsat-8, SRTM/ASTER DEMs

**Modeling**
- Python, MATLAB
- CNN / U-Net / SegFormer (waste segmentation)
- LSTM (spatio-temporal forecasting)
- ANN + Genetic Algorithm + Pattern Search (drilling/blasting optimization)
- SHAP (explainability)

**Infrastructure**
- Google Colab Pro+ / AWS GPU instances
- GPU-enabled workstation

## Project Scope

- Field data collection from marble sites in Buner, Swat, and Mohmand.
- Topographic characterization of mining terrain using DEMs.
- Satellite image processing via GIS tools and Google Earth Engine.
- AI model training and validation for detection, forecasting, and optimization.
- Drilling parameter optimization using GA-PS optimized ANN models.
- Prototype waste-monitoring dashboard.

## Repository Structure

```
├── data/                  # Raw & processed satellite/DEM/field data (not committed — see .gitignore)
├── notebooks/             # Exploratory analysis & model prototyping
├── src/
│   ├── preprocessing/     # Georeferencing, atmospheric correction, resampling
│   ├── gis/               # DEM & LULC feature derivation
│   ├── segmentation/      # CNN / U-Net / SegFormer waste detection models
│   ├── forecasting/       # LSTM spatio-temporal forecasting
│   ├── optimization/      # GA-PS optimized ANN for drilling/blasting
│   └── explainability/    # SHAP-based model interpretation
├── dashboard/             # Web dashboard (decision support system)
├── docs/                  # Proposal, reports, references
├── requirements.txt
└── README.md
```

## Getting Started

```bash
# Clone the repository
git clone https://github.com/Maira447/testt.git
cd ai-sustainable-marble-mining

# Create a virtual environment
python -m venv venv
source venv/bin/activate   # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
```

> Dataset access (satellite imagery, DEMs, field survey data) is documented separately in `docs/` due to size and licensing constraints.

## Timeline

**Duration:** August 2025 – June 2026

Key milestones: literature review → proposal approval → system design → data collection → preprocessing → AI/ML model development (segmentation, forecasting, optimization) → dashboard development → mine-site validation testing → research paper writing.

## Team

| Name | Registration No. | Role |
|---|---|---|
| Saira Zafar | 22PWCSE2128 | Co-Developer |
| Maira Zafar | 22PWCSE2106 | Co-Developer |

**Supervisor:** Dr. Safdar Nawaz Khan Marwat
**Co-Supervisor:** Dr. Saira Sherin

Department of Computer Systems Engineering, University of Engineering & Technology, Peshawar

## References

Full references are listed in [`docs/proposal.pdf`](docs/proposal.pdf). Key works include studies on GIS/remote-sensing based marble waste management, LSTM-based blasting vibration prediction, SHAP-based explainable AI for blast optimization, and hybrid GA/PSO-based drilling parameter optimization.
