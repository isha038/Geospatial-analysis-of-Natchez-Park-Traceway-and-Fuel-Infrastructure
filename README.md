# Geospatial-analysis-of-Natchez-Park-Traceway-and-Fuel-Infrastructure


## Overview  

This Jupyter Notebook focuses on analyzing the **Natchez Trace Parkway** in Mississippi, examining its geographical features and exploring practical questions related to travel.   

1. Extracting and visualizing the **Natchez Trace Parkway** from Mississippi's highway data.  
2. Addressing **range feasibility** for an electric car (Tesla Model 3) on a journey down the parkway.  
3. Performing spatial operations to determine required **recharge points** and travel ranges.  

The notebook uses **GeoPandas** for geospatial operations, distance calculations, and visualization.  



## Key Objectives  

1. Extract the **Natchez Trace Parkway** from the MARIS highway dataset.  
2. Visualize its spatial extent within Mississippi and beyond.  
3. Determine the feasibility of driving a Tesla Model 3 (base version) along the Natchez Trace Parkway with respect to:  
   - **Vehicle range** (based on real-world driving conditions).  
   - **Recharging stops** required to complete the journey in the month of July.  



## Data Source  

- **Highway Data**: Mississippi Automated Resource Information System (MARIS).  
- The focus is on the **Natchez Trace Parkway**, which is extracted into a separate GeoDataFrame for analysis.  



## Steps and Key Analysis  

### 1. Extracting the Natchez Trace Parkway  
- Filtered the highway data to isolate the **Natchez Trace Parkway** using its highway name attribute.  
- Created a new GeoDataFrame:  
   ```python  
   natchezTrace = msHighways.query("HWYNAME == 'NATCHEZ TRACE PKWY'")  
   msHighways = msHighways.drop(labels=45, axis=0)  
   natchezTrace.plot()  
   ```  

### 2. Visualizing the Natchez Trace Parkway  
- Plotted the parkway to understand its spatial extent, which spans Mississippi and continues into Tennessee.  
- The parkway resembles a sash across Mississippi, with no advertisements, billboards, or street lights, making it a unique travel experience.  

### 3. EV Travel Feasibility Analysis  
- Assumed a **Tesla Model 3 (base version)** with a full charge at the start of the Natchez Trace Parkway in July.  
- Investigated:  
   - Total distance of the parkway.  
   - Tesla Model 3's range under real-world conditions.  
   - Number of recharge stops required to complete the trip from the **top corner of Mississippi** to **Vicksburg**.  



## Key Findings  

1. **Distance and Range Analysis**  
   - The parkway's total distance was calculated using GeoPandas geometry.  
   - Tesla Model 3's base range (approximately **272 miles**) was factored into the feasibility study.  

2. **Number of Recharges**  
   - Based on the total distance and the Tesla's range, the notebook calculates the required recharges along the parkway.  


## Visualizations  

The following visualizations are included:  

- **Natchez Trace Parkway Map**:  
   - Spatial plot showing the parkway across Mississippi.  
- **Buffer and Distance Analysis**:  
   - Buffer zones and distances relevant to the EV range study.  



## Libraries and Tools  

- **GeoPandas**: Geospatial data analysis and visualization  
- **Pandas**: Data manipulation  
- **Matplotlib**: Plotting and visualizations  


### Installation  

Install the required libraries:  

```bash
pip install geopandas pandas matplotlib shapely fiona
```

---

## How to Run  

1. Clone this repository:  
   ```bash  
   git clone <repository-url>  
   cd <repository-folder>  
   ```  

2. Launch the notebook:  
   ```bash  
   jupyter notebook geoData2_SE.ipynb  
   ```  

3. Run the notebook cells step by step to see the analysis and results.  

---

## Results  

- The notebook provides a clear understanding of the Natchez Trace Parkway's geography.  
- It evaluates the feasibility of EV travel along the parkway, detailing the range and required stops for a Tesla Model 3.  



