# 🌤️ Weather Information Extraction Pipeline

This project extracts **average temperature at 18:00** for a grid of locations using the **Open-Meteo API**.

## 🚀 Pipeline Overview

### 1. Load Data
- Read city data (`abu_dhabi.csv`) containing latitude and longitude points.

### 2. Preprocess Locations
- Group locations by the first 3 digits of the latitudes and longitudes (after removing the decimal point).
- Create a **grid** by forming all combinations of unique lat/lng groups.

### 3. Adjust Coordinates
- Insert a decimal point after the first 2 digits to restore valid latitude and longitude formats.

### 4. Setup API Client

We used the API Call of the following link:

https://open-meteo.com/en/docs/historical-weather-api

- Initialize the **Open-Meteo API** client with:
  - Request caching
  - Automatic retries on failure

### 5. Retrieve Weather Data
- For each grid point:
  - Request **hourly temperature data** from **2025-04-10** to **2025-04-24**.
  - Extract and compute the **average temperature at 18:00**.

### 6. Save Results
- Save the results (`lat`, `lng`, `avg_temp_18`) into `weather_abu_dhabi.csv`.

## 📦 Output

- A file named `weather_abu_dhabi.csv` containing:
  - **Latitude** (`lat`)
  - **Longitude** (`lng`)
  - **Average Temperature at 18:00** (`avg_temp_18`)

---
