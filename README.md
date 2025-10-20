# 🧭 GeoBorehole3D — ArcGIS Python Toolbox

A **Python-based ArcGIS Toolbox** for visualizing and interpolating subsurface geology using borehole data through advanced **3D Kriging** workflows.

---

**Author:** Michael Attia, PhD, PE  
**Email:** [Michael.Attia@wsp.com](mailto:Michael.Attia@wsp.com)  
**Created:** October 30, 2023  
**Version:** 1.0  
**Organization:** WSP USA / Louisiana State University  

---

## 📖 Overview

**GeoBorehole3D** is a custom **ArcGIS Pro Python Toolbox (.pyt)** that automates the process of building 3D subsurface models from borehole datasets.  

The toolbox streamlines:
- Importing borehole CSV data and converting to 3D feature points  
- Building elevation-based 3D feature classes  
- Interpolating subsurface layers using **Empirical Bayesian Kriging 3D (EBK3D)**  

This enables users to efficiently visualize and interpret stratigraphic, lithologic, or hydrogeologic variations directly in **ArcGIS Pro**.

---

## ⚙️ Core Features

| Step | Description | ArcGIS Function |
|------|--------------|-----------------|
| 1️⃣ | Converts borehole CSV data into XY point features | `arcpy.management.XYTableToPoint` |
| 2️⃣ | Creates 3D features from elevation fields | `arcpy.ddd.FeatureTo3DByAttribute` |
| 3️⃣ | Interpolates volumetric surfaces via EBK 3D | `arcpy.ga.EmpiricalBayesianKriging3D` |

**Key Benefits:**
- Fully integrated with ArcGIS Pro 3D Analyst and Geostatistical Analyst  
- Automated workflow—minimal scripting required  
- Ideal for lithologic zoning, aquifer layer mapping, or contaminant plume visualization  

---

## 🧩 Requirements

| Component | Details |
|------------|----------|
| **ArcGIS Pro** | Version 2.8+ (tested on 3.0 and newer) |
| **Extensions** | 3D Analyst & Geostatistical Analyst |
| **Python** | 3.x (included with ArcGIS Pro) |
| **Input Data** | CSV file with: `x_field`, `y_field`, `elevation_field`, and `value_field` |

---

## 📦 Installation

### 🗺️ Add Toolbox to ArcGIS Pro

1. Open **ArcGIS Pro**  
2. In the **Catalog Pane**, right-click **Toolboxes → Add Toolbox**  
3. Browse to and select `GeoBorehole3D.pyt`  
4. The toolbox will now appear under **Toolboxes** in your project

---

## ▶️ Usage Guide

1. Open the tool in ArcGIS Pro:  
   **Toolboxes → GeoBorehole3D → Create 3D Borehole Model**

2. Provide the following parameters:
   - **Input CSV:** Borehole dataset (e.g., `Boreholes.csv`)  
   - **X Field:** X-coordinate (Albers)  
   - **Y Field:** Y-coordinate (Albers)  
   - **Elevation Field:** Top elevation of borehole interval  
   - **Value Field:** Indicator or lithologic code  
   - **Output Feature Class (2D):** Output shapefile or geodatabase path  
   - **Output Feature Class (3D):** 3D point feature output  
   - **Output EBK3D Layer:** Name for generated kriging volume  

3. Click **Run**. Progress messages will display in the **Geoprocessing Pane**.

**Results:**
- ✅ 2D feature class of borehole points  
- ✅ 3D feature class colored by elevation or lithology  
- ✅ EBK3D layer representing interpolated subsurface volume  

---

## 📊 Example Workflow

**Sample Input (`Boreholes.csv`):**

| x | y | Top_elev_m | Lithology |
|---|---|-------------|------------|
| 412345 | 3489012 | 35.2 | Sand |
| 412362 | 3489025 | 28.5 | Clay |
| 412381 | 3489044 | 18.3 | Gravel |

**Processing Steps:**
1. `XYTableToPoint` → **Borehole_Points**  
2. `FeatureTo3DByAttribute` → **Borehole_3D**  
3. `EmpiricalBayesianKriging3D` → **Borehole_EBK3D**

---

## 🧠 Tips & Best Practices

- Use **Albers Equal Area Conic (EPSG:102039)** for consistent spatial reference.  
- For large datasets, reduce the number of simulations or subset size in the Kriging tool for faster computation.  
- Ideal applications include:
  - 3D stratigraphic visualization  
  - Aquifer layer delineation  
  - Lithologic zone interpolation  
  - Contaminant plume analysis  

---

## 📚 Citation

If you use this toolbox in research or reports, please cite:

> **Attia, M. (2023).** *GeoBorehole3D: A Python-based ArcGIS Toolbox for Borehole Visualization and 3D Kriging.*  
> WSP USA / Louisiana State University.

---

## 📜 License

**MIT License © 2023 Michael Attia**

This software is open source and freely available for use, modification, and distribution with proper attribution.

---

## 💬 Contact

📧 **Email:** [Michael.Attia@wsp.com](mailto:Michael.Attia@wsp.com)  
🔗 **LinkedIn:** [linkedin.com/in/michaelgattia](https://www.linkedin.com/in/michaelgattia/)  

---

## 📁 Repository Structure

