# 🔥 Burn Severity Mapping via dNBR Composites & GEE-Driven Inference

This repository contains code and assets for the project:  
**"Quantitative Mapping of Post-Fire Severity using Multitemporal Spectral Differencing and Threshold-Based Stratification within the Google Earth Engine environment."**

Designed for scalable fire impact assessment across complex geographies using EO analytics and statistical abstraction.

---

## 📌 Project Overview

This pipeline leverages Earth observation analytics to compute the **differenced Normalized Burn Ratio (dNBR)** over fire-impacted landscapes.  
The process integrates MODIS burned area detection and Landsat-8 spectral differencing, culminating in pixel-level severity classification aligned with USGS standards.

All components are orchestrated via **Google Colab and Earth Engine**, enabling rapid prototyping and export.

---

## 📂 Repository Structure

- `notebooks/burn_severity_pipeline.ipynb`: Main pipeline notebook (GEE + Python)
- `datasets/`: Input region data (e.g., ROI GeoJSON files)
- `outputs/`:
  - `CSVs/`: Exported dNBR and severity samples
  - `GeoTIFFs/`: Output rasters (dNBR, classified burn severity)
  - `PNGs/`: Analytical plots (histograms, boxplots, severity class counts)
- `README.md`: Project overview and usage documentation

---

## 🧠 Methods

- **Data Acquisition**  
  Filtered Landsat-8 SR imagery (cloud-masked) and MODIS MCD64A1 burned area polygons

- **Spectral Indexing**  
  NBR derived from SWIR2 and NIR bands; dNBR calculated from temporal composites

- **Severity Classification**  
  Categorical segmentation of dNBR using USGS breakpoints

- **Sampling & Export**  
  Rasters exported to GeoTIFF; samples exported to CSV with geometry attributes

- **Post-Processing**  
  Statistical profiling (distribution, class-wise variance, density curves)

---

## 🗺️ Region of Interest

Default analysis targets the **Blue Mountains region (NSW, Australia)**, affected by the 2019–2020 Black Summer fire season.  
The workflow is ROI-agnostic and supports any GeoJSON-defined polygon.

---

## 📦 How to Use

Deploy the pipeline within a Colab-GEE environment.  
Execution yields severity-classified rasters, derived metrics, and analytical plots.  
Parametric tuning (temporal window, cloud threshold, sampling resolution) is modular and configurable.

---

## 📡 Data Sources

- **Landsat-8 SR**: `LANDSAT/LC08/C02/T1_L2`  
- **MODIS Burned Area**: `MODIS/006/MCD64A1`  
- **Region Geometry**: User-supplied GeoJSON polygon

---
