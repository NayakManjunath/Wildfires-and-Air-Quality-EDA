# Wildfire Activity vs Air Quality Analysis

## Overview
This project analyzes the relationship between **wildfire activity** and **air quality** by combining two independent datasets:
- Wildfire event data
- Air Quality Index (AQI) data

The goal is to understand whether increased wildfire activity is associated with worsening air quality, using a simple but effective daily-level comparison.

---

## Datasets Used

### 1. Wildfire Dataset (`wf`)
Expected columns:
- `start_date` – Date when a wildfire event started

Each row represents a wildfire event.

### 2. Air Quality Dataset (`aq`)
Expected columns:
- `date` – Observation date
- `AQI Value` or `PM2.5` – Air quality metric for the day

Each row represents air quality measurements for a specific location and date.

---

## Analysis Logic

1. Convert date columns to datetime format
2. Aggregate wildfire data to get **daily wildfire counts**
3. Aggregate AQI data to get **daily average air quality**
4. Merge both datasets on the date column
5. Visualize the relationship using a bivariate scatter plot

This keeps both datasets on the same temporal granularity, making the comparison meaningful.

---

## Visualization Produced

### Daily Average AQI vs Wildfire Count
- **X-axis:** Number of wildfires per day
- **Y-axis:** Average AQI (or PM2.5) for the same day

This plot helps identify whether air quality degrades as wildfire activity increases.

---

### Project Structure 
project_wildfire_aqi_eda/
├─ notebooks/
│  └─ EDA_Wildfire_AirQuality.ipynb
├─ data/
│  ├─ wildfires.csv
│  └─ aqi.csv
├─ artifacts/
│  ├─ wildfire_count_by_year.png
│  ├─ acres_burned_dist.png
│  ├─ pm25_distribution.png
│  ├─ pm25_vs_wildfire_count.png
│  ├─ wildfires_cleaned.csv
│  └─ aqi_cleaned.csv
├─ src/
│  └─ utils.py
└─ README.md

### Key Insights

Higher wildfire counts often align with poorer air quality

PM2.5 and AQI are sensitive indicators of wildfire impact

Daily aggregation reduces noise and improves interpretability

### Tools & Libraries

Python

Pandas

Matplotlib

### Possible Extensions

Lag analysis (wildfires today vs AQI tomorrow)

City- or region-level comparisons

Correlation and regression modeling

Interactive dashboard using Streamlit
