# Task-05: Traffic Accident Analysis

**Internship:** Prodigy InfoTech — Data Science Internship
**Task:** Analyze traffic accident data to identify patterns related to road conditions, weather, and time of day, and visualize accident hotspots and contributing factors.

---

## 📌 Project Overview

Road accidents are influenced by a mix of environmental, temporal, and infrastructural factors. In this task, I explored a large-scale US traffic accident dataset to understand:

- When accidents are most likely to occur (time of day, day of week, month)
- How weather conditions affect accident frequency and severity
- How road/environmental features (junctions, signals, crossings, etc.) relate to accidents
- Where accidents are geographically concentrated (hotspots)

The goal was to turn raw accident records into clear, visual insights that could help identify high-risk conditions and locations.

---

## 📂 Dataset

**Source:** [US Accidents Dataset — Kaggle](https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents)
**Author:** Sobhan Moosavi

The dataset contains several million records of traffic accidents across the United States, collected from multiple APIs that provide streaming traffic incident data. Each record includes details such as:

- Location (latitude, longitude, city, state)
- Date and time of the accident
- Weather conditions (temperature, visibility, precipitation, wind speed, etc.)
- Road features (traffic signal, junction, crossing, stop sign, etc.)
- Severity of the accident



---

## 🛠️ Tools & Libraries Used

- **Python** — core language for analysis
- **Pandas** — data cleaning and manipulation
- **NumPy** — numerical operations
- **Matplotlib / Seaborn** — statistical visualizations
- **Folium** — interactive geographic hotspot mapping
- **Jupyter Notebook** — analysis environment

---

## 🔍 Approach

1. **Data Cleaning**
   - Removed duplicate and irrelevant columns
   - Handled missing values in weather and location fields
   - Converted date/time columns into usable formats

2. **Feature Engineering**
   - Extracted hour, day of week, and month from timestamps
   - Categorized weather conditions into simplified groups
   - Flagged presence of road features (signal, junction, crossing, etc.)

3. **Exploratory Data Analysis (EDA)**
   - Accident frequency by hour of day and day of week
   - Accident frequency by weather condition
   - Accident severity distribution across conditions
   - Correlation between road features and accident counts

4. **Geographic Hotspot Visualization**
   - Plotted accident density on an interactive map using Folium
   - Highlighted high-frequency accident zones

---

## 📊 Key Insights

- Accidents peak during **morning (7–9 AM)** and **evening (4–6 PM)** rush hours, aligning with commute times.
- **Clear weather** accounts for the highest raw number of accidents (since it's the most common condition), but **rain, fog, and snow** show a noticeably higher accident rate relative to their frequency.
- Roads near **junctions, traffic signals, and crossings** show a higher concentration of accidents than open stretches.
- Certain metro/urban areas emerge as clear **hotspots** with dense clusters of incidents.
- Weekdays see more accidents than weekends, consistent with commuter traffic patterns.



---

## 📁 Project Structure

```
Task-05-Traffic-Accident-Analysis/
│
├── data/                 # Dataset (or link/reference, not uploaded due to size)
├── notebook/             # Jupyter notebook with full analysis
├── visuals/              # Exported charts and hotspot maps
└── README.md             # Project documentation
```

---

## ▶️ How to Run

1. Clone this repository
2. Download the dataset from the [Kaggle link](https://www.kaggle.com/datasets/sobhanmoosavi/us-accidents) and place it in the `data/` folder
3. Install required libraries:
   ```
   pip install pandas numpy matplotlib seaborn folium
   ```
4. Open the notebook and run all cells:
   ```
   jupyter notebook notebook/traffic_accident_analysis.ipynb
   ```

---

## 🙌 Acknowledgements

- Dataset by **Sobhan Moosavi** on Kaggle
- Task provided as part of the **Prodigy InfoTech Data Science Internship**

---

