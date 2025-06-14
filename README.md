# 📦 DHL Facilities Network Analysis

**Strategic Analysis and Optimization of DHL Facility Network Across the United States**

## 🗂️ Overview
This project analyzes DHL’s facility data using Python and geospatial tools to assess data quality, identify spatial and operational trends, and develop recommendations to improve network efficiency. The analysis focuses on depots, stations, and pickup points, with an emphasis on clustering, utilization, and strategic planning.

## 📁 Data Description

### Files Used:
- `DHL_Facilities_Data.csv`: Main dataset containing 18 attributes per facility (e.g., type, geolocation, ZIP, status, placement category, and last pickup timestamp).
- `US_ZipCode_Data.xlsx`: ZIP-code level reference file used for geographic validation and population normalization.
- `DHL_facilities_Network_analysis.ipynb`: Jupyter Notebook containing full analysis, visualizations, and insights.

### Key Columns from CSV:
- `FEATURE_ID`, `LOCATION_TY`, `PLACEMENT`, `STATUS`
- `CITY`, `STATE`, `ZIP`
- `LATITUDE`, `LONGITUDE`
- `LAST_PICKUP`, `MATCH_STATUS`

## 🧹 Data Cleaning & Quality Profiling

The data cleaning process included:

1. **Null and Anomaly Detection**:
   - Quantified null values across all columns
   - Flagged invalid ZIP codes and mismatched CITY/STATE combinations using the reference dataset
   - Identified missing or incorrect geolocation data

2. **Data Type Inspection & Standardization**:
   - Converted `LAST_PICKUP` to datetime
   - Ensured ZIP codes were standardized to 5-digit strings

3. **Geo-Validation**:
   - Used US ZIP reference data to confirm location validity
   - Labeled facilities by MSA

## 📊 Exploratory & Geospatial Analysis

### Geographic Distribution:
- Visualized facility density by `STATE` and `Metropolitan Statistical Area (MSA)`
- Ranked top 10 and bottom 10 regions by both raw count and population-normalized count

### Operational & Categorical Insights:
- Generated stacked bar charts of `LOCATION_TY` within each `PLACEMENT` category
- Compared type/placement mix across top 3 states
- Analyzed `STATUS` breakdown by state and location type

### Temporal Trends:
- Analyzed pickup patterns by:
  - **Month** (seasonality)
  - **Weekday** (operational load)
- Calculated dormancy (facilities inactive in the last 30, 60, 90 days)

## 💡 Recommendations

### Expansion Opportunities:
- Identified 5 underserved MSAs based on low facility density
- Highlighted one high-growth state for facility expansion

### Resource Allocation:
- Recommended months and weekdays for deploying additional pickup crews
- Suggested adjustments to the mix of Depots, Stations, and Pickup Points in urban clusters

## 🛠️ Tools & Technologies
- **Python** (Pandas, GeoPandas, Seaborn, Matplotlib, Folium)
- **Jupyter Notebook**
- **Excel (ZIP reference data)**
