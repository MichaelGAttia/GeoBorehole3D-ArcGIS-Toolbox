# 🧭 GeoBorehole3D-ArcGIS-Toolbox

A Python-based **ArcGIS Toolbox** for visualizing and interpolating subsurface geology using borehole data with 3D kriging.

---

**Author:** Michael Attia, PhD, PE  
**Email:** [Michael.Attia@wsp.com](mailto:Michael.Attia@wsp.com)  
**Created:** October 30, 2023  
**Version:** 1.0  

---

## 📖 Overview

**GeoBorehole3D** is a custom **ArcGIS Python Toolbox (.pyt)** designed to automate the visualization and creation of 3D geological models from borehole data.

This tool enables users to:
- Import borehole CSV data and create 3D point features.
- Convert borehole points into 3D features using elevation attributes.
- Interpolate subsurface layers using **Empirical Bayesian Kriging 3D (EBK3D)**.

The workflow provides a robust approach for visualizing stratigraphy, lithology, or other vertical subsurface attributes directly in **ArcGIS Pro**.

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
- **3D Analyst** and **Geostatistical Analyst** extensions  
- **Python 3.x** (installed with ArcGIS Pro)  
- **Input CSV File** must include the following fields:
  - `x_field` – X coordinate (Albers)
  - `y_field` – Y coordinate (Albers)
  - `elevation_field` – Top elevation
  - `value_field` – Indicator or lithologic code

---

## 📦 Installation

### 🗺️ Load Toolbox in ArcGIS Pro

1. Open **ArcGIS Pro**  
2. Go to the **Catalog Pane** → Right-click **Toolboxes** → **Add Toolbox**  
3. Browse to `GeoBorehole3D.pyt` and click **OK**  

The toolbox will appear under your **Toolboxes** folder.

---

### ▶️ How to Use the Tool

1. Open the tool:  
   `ArcGIS Pro → Toolbox → GeoBorehole3D → CustomToolbox`

2. Provide the following inputs:
   - **Input CSV File:** e.g., `Boreholes.csv`  
   - **x Albers:** X-coordinate field  
   - **y Albers:** Y-coordinate field  
   - **Elevation Field:** Top elevation of borehole interval  
   - **Value Field:** Indicator/lithologic code  
   - **Output Feature Class:** Path for generated 2D point feature class  
   - **Output 3D Feature Class:** Path for generated 3D features  
   - **Output Kriging Layer:** Name for generated EBK 3D layer  

3. Run the tool — progress messages will display in the **Geoprocessing Pane**.

Once complete, your ArcGIS project will include:
- ✅ 2D feature class of borehole points  
- ✅ 3D feature class symbolized by elevation  
- ✅ EBK 3D layer representing interpolated subsurface properties  

---

## 📊 Example

**Input CSV**

| x | y | Top_elev_m | R |
|---|---|-------------|---|
| 412345 | 3489012 | 35.2 | Sand |
| 412362 | 3489025 | 28.5 | Clay |
| 412381 | 3489044 | 18.3 | Gravel |

**Output Workflow**

- XYTableToPoint → Borehole_Points
- FeatureTo3DByAttribute → Borehole_3D
- EmpiricalBayesianKriging3D → Borehole_EBK3D



---

## 🧠 Notes

- Ensure all coordinates are in **Albers Equal Area Conic (EPSG:102039)** or adjust the spatial reference in the code.  
- For large datasets, reduce the number of simulations or subset size in the Kriging tool for faster performance.  
- Ideal applications:
  - Lithologic zoning  
  - Aquifer layer delineation  
  - Subsurface property interpolation  

---

## 🧾 Citation

If you use this tool in a publication or report, please cite as:

> Attia, M. (2023). *GeoBorehole3D: A Python-based ArcGIS Toolbox for Borehole Visualization and 3D Kriging.*  
> WSP USA / Louisiana State University.

---

## 📜 License

**MIT License © 2023 Michael Attia**

You are free to use, modify, and distribute this tool with attribution.

---

## 💬 Contact

For questions, suggestions, or collaboration opportunities:

📧 [Michael.Attia@wsp.com](mailto:Michael.Attia@wsp.com)  
🌐 [LinkedIn](https://www.linkedin.com)([mailto:Michael.Attia@wsp.com](https://www.linkedin.com/in/michaelgattia/))   

---

## 📁 Repository Structure
GeoBorehole3D/
├── GeoBorehole3D.pyt
├── example_data/
│ └── Boreholes.csv
├── README.md
├── LICENSE
└── .gitignore


