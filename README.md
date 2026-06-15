# US Traffic Accidents Data Analysis (2016–2023) 📈📊

## Overview 
In this project, I analyzed a massive dataset of US traffic accident reports spanning from February 2016 to March 2023. The dataset consists of approximately 7.7 million records and 48 distinct features. By utilizing **Python** for data wrangling/cleaning and **Tableau** for exploratory data analysis (EDA), I extracted meaningful insights regarding accident hotspots, seasonal trends, and environmental contributing factors. 

[👉 **Click here to view the interactive Tableau Dashboard**](#) *(Add your Tableau Public link here)*

## Introduction
This extensive dataset captures car accidents across 49 states in the USA. It aggregates real-time traffic incident data from multiple APIs, sourcing information from diverse entities including the US and state departments of transportation, law enforcement agencies, traffic cameras, and embedded road sensors.

### Objective
The goal of this analysis is to identify key areas of concern and potential pain points on US roads. By uncovering these insights, this project aims to provide valuable information to policymakers, enabling strategic recommendations to collectively reduce traffic accidents nationwide and make commutes safer.

### Data Dictionary
| Column | Description |
| :--- | :--- |
| **ID** | Unique identifier of the accident record. |
| **Source** | Source of raw accident data. |
| **Severity** | 1 (least impact on traffic/short delay) to 4 (significant impact/long delay). |
| **Start/End_Time** | Start and end time of the accident in the local timezone. |
| **Start/End_Lat & Lng** | GPS coordinates for the start and end points of the accident. |
| **Distance(mi)** | Length of the road extent affected by the accident in miles. |
| **Description** | Human-provided description of the accident. |
| **Location Info** | `Street`, `City`, `County`, `State`, `Zipcode`, `Country`, `Timezone`. |
| **Weather_Timestamp** | Time-stamp of weather observation record (local time). |
| **Weather Metrics** | `Temperature(F)`, `Wind_Chill(F)`, `Humidity(%)`, `Pressure(in)`, `Visibility(mi)`, `Wind_Direction`, `Wind_Speed(mph)`, `Precipitation(in)`. |
| **Weather_Condition** | Current weather state (rain, snow, thunderstorm, fog, etc.). |
| **POI Annotations** | Nearby points of interest: `Amenity`, `Bump`, `Crossing`, `Give_Way`, `Junction`, `No_Exit`, `Railway`, `Roundabout`, `Station`, `Stop`, `Traffic_Calming`, `Traffic_Signal`, `Turning_Loop`. |
| **Time of Day** | Period of day based on `Sunrise_Sunset`, `Civil_Twilight`, `Nautical_Twilight`, and `Astronomical_Twilight`. |

## Purpose & Research Questions
This analysis aims to answer the following core questions:

* **Trend Analysis:** What is the overall trend in traffic accidents over the specified period? Are there significant year-over-year increases or decreases?
* **Seasonal Patterns:** Do traffic accidents follow a seasonal pattern (e.g., higher frequencies during winter or summer)?
* **Temporal Analysis:** During which days of the week and times of the day do most accidents occur?
* **Contributing Factors:** What are the primary environmental and infrastructural factors contributing to these accidents?

## Methodology: Steps Taken
For the complete Python code, please refer to the notebooks in this repository. The general data wrangling process included:
1. **Missing Value Assessment:** Calculated the percentage of null values for each column.
2. **Imputation vs. Deletion:** Decided whether to fill missing data with statistical means or drop the rows entirely based on data integrity.
3. **Outlier Inspection:** Carefully reviewed columns for extreme outliers.
4. **Standardization:** Transformed specific measurements to ensure consistency.
5. **Dimensionality Reduction:** Consolidated values in heavily fragmented columns (like Weather Conditions) into a more manageable format for better analysis.
6. **Export:** Transitioned the cleaned dataset into Tableau for visualization.

## Visualizations & Exploratory Analysis
*Please refer to the Tableau dashboard linked at the top of this document for interactive drill-downs.*

* **Geographic Hotspots:** Accidents frequently occur around the coastal and border edges of the US. 
* **State-by-State Discrepancies:** California, Florida, Texas, South Carolina, and New York lead in accident volume. Conversely, states like South Dakota and Vermont have the lowest. The gap is massive—California recorded 7,080x more cases than South Dakota, likely due to a mix of population density and reporting coverage.
* **City-Level Data:** Miami, Houston, Los Angeles, Charlotte, and Dallas report the highest occurrences. Interestingly, 761 cities recorded only 1 accident from 2016–2023, suggesting discrepancies in media or sensor coverage.
* **Severity Trends:** While total traffic accidents have doubled since 2017, the most severe accidents (Severity 3) have actually decreased, while moderate accidents (Severity 2) are driving the overall volume increase.
* **Seasonal & Monthly Spikes:** Fall and Winter dominate accident occurrences. November and December see the highest spikes (likely due to holiday travel, crowded streets, and snow), while July sees the lowest. A concerning recent spike was also observed in Spring 2022.
* **Temporal Trends:** Weekdays experience significantly more accidents than weekends. The hourly distribution peaks tightly around commuting hours: **6:00 AM – 8:00 AM** and **3:00 PM – 5:00 PM**.
* **Weather & Infrastructure:** 
    * Most accidents happen in standard weather, but high humidity and low visibility (under 11 miles) correlate strongly with increased accidents. 
    * Severe weather (storms/rain) heavily skews toward Severity 3, while tornadoes yield the highest proportion of Severity 4 accidents.
    * Infrastructurally, accidents cluster heavily around traffic signals, crossings, and junctions, rather than stop signs or stations.

## Key Insights 💡
1. **Accident Volume is Scaling:** Total traffic accidents have doubled since 2017.
2. **Commuter Danger Zones:** Weekdays and traditional commuting hours (6-8 AM & 3-5 PM) are the highest-risk windows.
3. **Seasonal Hazards:** The Fall and Winter seasons—particularly November and December—contribute to the highest accident rates.
4. **Visibility is Crucial:** A sharp drop in accidents occurs when visibility exceeds 11 miles, reinforcing that clear sightlines are vital for road safety.
5. **Behavioral Impact:** Weather conditions that induce high humidity or limit visibility likely alter driver behavior negatively, driving up incident rates.

## Challenges Faced
* **Data Ambiguity:** Initial data exploration required extensive research to understand the specific units and meanings behind certain columns.
* **High Cardinality:** The `Weather_Condition` column contained over 100 distinct descriptions. I resolved this by extracting keywords and creating standardized boolean (True/False) columns.
* **Processing Constraints:** Handling a 3.2GB file with 7.7 million rows was computationally expensive. I optimized the workflow by sampling 2% of the data to build and test the cleaning pipeline before applying it to the entire dataset.

## Future Steps
* **Machine Learning Integration:** Implement predictive modeling to weight which factors (weather, time, location) have the highest predictive power for accident severity.
* **Population Normalization:** Incorporate population density metrics by state and county to calculate accidents *per capita*, yielding a more accurate risk assessment.
* **Source Analysis:** Further investigate the APIs and reporting bodies (Source 1, 2, 3) to understand reporting biases and improve data clarity.

## Conclusion
The analysis of US traffic accidents from 2016 to 2023 reveals a concerning annual increase in incidents. Commuting hours, winter months, and low-visibility conditions remain the most significant danger zones. Addressing these escalating issues requires a multi-faceted approach. By leveraging these insights, government agencies, local authorities, and the public can collaborate to implement targeted infrastructure improvements and safety campaigns, ultimately striving toward safer roads across the nation.
