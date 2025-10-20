# GeoBorehole3D-ArcGIS-Toolbox
A Python-based ArcGIS Toolbox for visualizing and interpolating subsurface geology using borehole data with 3D kriging.

**Author:** Michael Attia, PhD, PE  
**Email:** Michael.Attia@wsp.com  
**Created:** October 30, 2023  
**Version:** 1.0  

---

## 📖 Overview

**GeoBorehole3D** is a custom **ArcGIS Python Toolbox (.pyt)** designed to automate the visualization and creation of 3D geological models from borehole data.

This tool allows users to:
- Import borehole CSV data and create 3D point features.
- Convert borehole points to 3D features using elevation attributes.
- Interpolate subsurface layers using **Empirical Bayesian Kriging 3D** (EBK3D).

The workflow helps visualize stratigraphic indicators, lithology, or other vertical attributes in a fully 3D environment within ArcGIS Pro.

---

## ⚙️ Features

| Step | Description | ArcGIS Function Used |
|------|--------------|----------------------|
| 1 | Converts borehole CSV data to XY point features | `arcpy.management.XYTableToPoint` |
| 2 | Builds 3D feature classes from elevation fields | `arcpy.ddd.FeatureTo3DByAttribute` |
| 3 | Interpolates volumetric surfaces via 3D Kriging | `arcpy.ga.EmpiricalBayesianKriging3D` |

---

## 🧩 Requirements

- **ArcGIS Pro 2.8+** (tested on 3.0 and newer)
- **3D Analyst** and **Geostatistical Analyst** extensions enabled
- Python 3.x (installed with ArcGIS Pro)
- Input borehole CSV file with the following columns:
  - `x_field` – X coordinate (Albers)
  - `y_field` – Y coordinate (Albers)
  - `elevation_field` – Top elevation
  - `value_field` – Indicator/lithologic code

---

## 📦 Installation

1. Clone or download this repository:
   ```bash
   git clone https://github.com/YourUsername/GeoBorehole3D.git
