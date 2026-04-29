README 2 — Technical Workflow & Geospatial Analysis
🛰️ Parcel Eligibility Analysis — Python & GIS Workflow
📌 Overview
This project implements a geospatial data processing pipeline to classify agricultural parcels based on their eligibility for a carbon farming project.
The workflow is built using Python and GIS tools, ensuring automation, scalability, and reproducibility.

🧾 Input Data
The analysis integrates multiple spatial datasets:
1. Parcel Dataset
•	Source: Internal database 
•	Format: Vector (GeoPackage / Shapefile) 
2. Land Cover Data
•	Source: Esri Sentinel-2 Land Cover 
•	Format: Raster 
•	Purpose: Identify land-use constraints 
3. Protected Areas
•	Source: Open-source shapefiles 
•	Purpose: Exclude environmentally protected zones 
4. Administrative Boundaries
•	Purpose: Provide geographic context and validation 

⚙️ Workflow
Step 1 — Data Preparation
In Qgis
•	Load datasets into Jupyter Notebook 
•	Clean geometries (fix invalid shapes) 
•	Harmonize Coordinate Reference Systems (CRS) 
In python
Clean and restructure parcels attributes

Step 2 — Constraint Layer Creation
•	Extract constraint classes from land cover raster (e.g., forest, water, urban) 
•	Convert raster to vector format 
•	Merge with protected areas dataset 
•	Create a unified constraint layer 

Step 3 — Spatial Classification
Each parcel is evaluated against the constraint layer:
•	Eligible → No intersection 
•	Partially Eligible → Partial intersection 
•	Ineligible → Fully within constraint 

Step 4 — Output Generation
•	Export results as GeoPackage (.gpkg) 
•	Load into QGIS for visualization and validation 
•	Enable further GIS analysis and stakeholder review 

🧠 Technical Highlights
•	Automated geospatial classification using Python 
•	Efficient handling of large datasets 
•	Clean and modular workflow design 
•	Integration between raster and vector data 
•	Ready for scaling across multiple regions 

🛠️ Tools & Libraries
•	Python 
o	GeoPandas 
o	Rasterio 
o	Shapely 
o	Pandas
o	numpy
•	Jupyter Notebook 
•	QGIS 

🚀 Potential Improvements
•	Automated reporting pipelines 

📊 Output Example
Each parcel receives an eligibility label:
Parcel ID	Eligibility Status
P001	Eligible
P002	Partially Eligible
P003	Ineligible


