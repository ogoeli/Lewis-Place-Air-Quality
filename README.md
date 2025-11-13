# Lewis Place Environmental and Land Use Analysis

This Google Earth Engine (GEE) script performs a comprehensive environmental and land use analysis for **Lewis Place**, including:

- Land use breakdown (residential, industrial, parks)
- Air pollution analysis (PM2.5, Absorbing Aerosol Index (AAI), Carbon Monoxide (CO))
- Heat index mapping using MODIS LST
- Land use change detection using Sentinel-2 NDVI and NDBI (e.g., for tornado damage assessment)
- Visualization and export of results for further analysis

---

## **Features**

1. **Boundary Filtering**
   - Extracts the Lewis Place boundary from a larger dataset.
   - Clips all other datasets (parks, streets, trees, land use) to this boundary.

2. **Land Use Analysis**
   - Separates parcels into residential, industrial, and park areas.
   - Computes total area and percentage coverage for each land use type.
   - Generates a pie chart visualization of land use distribution.

3. **Air Pollution Analysis**
   - PM2.5: Daily, monthly, and yearly datasets scaled and clipped to Lewis Place.
   - AAI: Sentinel-5P absorbing aerosol index analysis per region.
   - CO: Sentinel-5P carbon monoxide column number density analysis per region.
   - Generates time-series charts and exports data as CSV.

4. **Heat Index Analysis**
   - Uses MODIS LST (MOD11A2) to compute monthly heat index per land use region.
   - Generates time-series charts and exports results to CSV.

5. **Land Use Change Detection**
   - Uses Sentinel-2 data to compute NDVI (vegetation) and NDBI (built-up) indices.
   - Compares “before” and “after” periods (e.g., tornado events).
   - Visualizes changes, calculates summary statistics, and exports GeoTIFFs.
   - Optional thresholded masks for significant vegetation loss or new built-up areas.

---

## **Datasets**

- **Local Datasets:**
  - `lewisPlace_ALL`: AOI boundary
  - `cityParks`, `cityStreets`, `cityTrees`, `landUse`: Various city features

- **Remote Sensing Data:**
  - PM2.5: GHAP Daily, Monthly, and Yearly collections
  - Sentinel-5P: AAI (`COPERNICUS/S5P/NRTI/L3_AER_AI`) and CO (`COPERNICUS/S5P/NRTI/L3_CO`)
  - MODIS LST: `MODIS/061/MOD11A2`
  - Sentinel-2: Surface Reflectance (`COPERNICUS/S2_SR_HARMONIZED`)

---

## **Usage**

1. Open the script in **Google Earth Engine Code Editor**.
2. Modify the AOI if analyzing a different area.
3. Adjust date ranges for air pollution, heat, or land use change analysis.
4. Run the script.
5. View visualizations in the GEE map console.
6. Export CSV or GeoTIFF outputs to Google Drive.

---

## **Outputs**

- **CSV Tables:**  
  - PM2.5 by region  
  - AAI by region  
  - CO by region  
  - Heat index (LST) by region  

- **GeoTIFF Images:**  
  - NDVI and NDBI change maps  
  - Vegetation loss mask  
  - Built-up gain mask  

- **Charts:**  
  - Pie chart of land use distribution  
  - Time-series charts of air pollution and heat by land use type  

---

## **Author**

Ogonna P. Eli, Ph.D. Student  
ECOSAIL Lab, Department of Informatics and Computing,  
Northern Arizona University

---

## **License**

MIT License

