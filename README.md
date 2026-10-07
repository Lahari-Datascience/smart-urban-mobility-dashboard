# Smart Urban Mobility and Traffic Intelligence Dashboard

## 📊 Project Overview

The **Smart Urban Mobility and Traffic Intelligence Dashboard** is a Power BI project developed as part of the **Infosys Springboard Virtual Internship**.

The project analyzes urban mobility and transportation data to identify patterns in:

- 🚕 Ride-Hailing
- 🛵 Micromobility
- 🚌 Mass Transit
- 🌦️ Weather impact
- 📈 Transportation demand
- ⚡ Average speed
- 📍 Location-wise mobility
- ♿ Mobility access and equity
- 🔮 Demand forecasting
- 🚨 Anomaly detection

The project was developed progressively through **four milestones**, starting from data preparation and dashboard design and extending to advanced mobility analytics, equity analysis, executive reporting, forecasting, and anomaly detection.

---

## 🎯 Project Objective

The main objective of this project is to transform raw urban mobility data into an **interactive Power BI dashboard** that helps users understand transportation patterns and make data-driven observations.

The dashboard provides different levels of analysis, from detailed mobility patterns to executive-level summaries.

---

## 🛠️ Tools & Technologies

- **Microsoft Power BI Desktop**
- **Power Query**
- **DAX (Data Analysis Expressions)**
- **Microsoft Excel**
- **GitHub**

---

## 📁 Dataset

The primary dataset used in the project is:

`Smart_City_Mobility_Sample_500.xlsx`

The dataset contains **500 sampled trip records** from a larger Smart City Mobility dataset.

### Important fields include:

- Route ID
- Location
- Vehicle Type
- Transport Mode
- Average Speed (KMH)
- Passenger Count
- Temperature
- Weather
- Rainfall
- Date
- Vehicle Count
- Mobility Segment

Each row represents a recorded mobility trip.

---

# 🏗️ Data Preparation & Modeling

The original dataset was transformed into a structured **star-schema data model**.

### Main tables

- `Fact_mobility`
- `Dim_location`
- `Dim_route`
- `DateTable`

The `Fact_mobility` table acts as the central fact table.

Relationships were created between the fact table and dimension tables using:

- Location
- Route ID
- Date

The relationships use a **one-to-many (1:*) structure** with single-direction filtering.

---

# 🧹 Data Cleaning

Data preparation was performed using Power Query and Power BI.

Major preparation activities included:

- Loading the Excel dataset into Power BI
- Creating fact and dimension tables
- Removing duplicate values from dimension tables
- Checking and correcting data types
- Creating a Date table
- Establishing relationships
- Sorting month names in calendar order

---

# 🧮 DAX & Measures

Several DAX measures were created for the analysis.

### Total Trips

```DAX
Total Trips =
COUNTROWS(Fact_mobility)
````

### Average Speed

```DAX
Avg Speed =
AVERAGE(Fact_mobility[Average Speed (KMH)])
```

### Total Passengers

```DAX
Total Passengers =
SUM(Fact_mobility[Passenger Count])
```

### Total Vehicle Count

```DAX
Total Vehicle Count =
SUM(Fact_mobility[Vehicle Count*])
```

### Average Temperature

```DAX
Avg Temperature =
AVERAGE(Fact_mobility[Temperature (C)])
```

### Average Rainfall

```DAX
Avg Rainfall =
AVERAGE(Fact_mobility[Rainfall (MM)])
```

### Distinct Routes

```DAX
Distinct Routes =
DISTINCTCOUNT(Fact_mobility[Route ID])
```

### Distinct Locations

```DAX
Distinct Locations =
DISTINCTCOUNT(Fact_mobility[Location])
```

---

# 🚕 Mobility Segmentation

A **Mobility Segment** classification was created to organize the transportation data into meaningful categories.

The main segments are:

| Mobility Segment | Description            |
| ---------------- | ---------------------- |
| Mass Transit     | Bus / Public transport |
| Micromobility    | Motorcycle / EV        |
| Ride-Hailing     | Taxi / Car             |
| Other            | Remaining records      |

This segmentation allows the dashboard to analyze different mobility types separately and compare them with each other.

---

# 📌 Milestone 1 — Data Modeling, DAX & Dashboard Design

Milestone 1 focused on building the foundation of the Power BI project.

### Main activities

* Dataset preparation
* Data cleaning
* Star-schema modeling
* Table relationships
* DAX calculations
* Dashboard design
* KPI cards
* Slicers
* Donut chart
* Bar chart
* Line chart
* Detailed route-level table

### Initial dashboard included:

* Total Trips
* Average Speed
* Total Passengers
* Total Vehicle Count
* Trips by Transport Mode
* Trips by Vehicle Type
* Monthly trip trends
* Route-level details

---

# 🗺️ Milestone 2 — Geospatial & Transit Analytics

Milestone 2 extended the initial dashboard with **geospatial and transit analysis**.

The dashboard was enhanced with:

* Geographic analysis
* Mobility distribution
* Demand heatmaps
* Location-based analysis
* Geographic drill-down
* Transit performance analysis
* Weather filtering
* Time-based filtering

This milestone helped provide a location-oriented view of urban mobility.

---

# 🚕 Milestone 3 — Mobility & Demand Intelligence

Milestone 3 expanded the project into detailed mobility and demand analysis.

## Page 1 — Ride-Hailing Intelligence

This page focuses on the **Ride-Hailing** segment.

It analyzes:

* Ride-Hailing trip volume
* Average speed
* Passenger patterns
* Monthly trends
* Location-wise activity
* Weather-based activity
* Route-level information

---

## 🛵 Page 2 — Micromobility Analytics

This page focuses on **Micromobility**.

It analyzes:

* Micromobility trips
* Average speed
* Passenger patterns
* Monthly trends
* Location-wise activity
* Weather-based activity
* Route-level details

---

## 📊 Page 3 — Modal Substitution Analysis

This page compares different mobility segments.

The main segments include:

* Mass Transit
* Micromobility
* Ride-Hailing
* Other

The objective is to understand how transportation usage is distributed across different mobility modes.

---

## 🌦️ Page 4 — Weather Sensitivity

This page analyzes how weather conditions relate to mobility activity.

Weather conditions include:

* Clear
* Cloudy
* Rain
* Storm
* Fog

The analysis includes:

* Trip volume by weather
* Average speed
* Rainfall
* Temperature
* Relationship between rainfall and speed

---

## 🔮 Page 5 — Demand Forecasting

This page analyzes historical transportation demand and provides future projections.

It includes:

* Demand trends
* Monthly trip analysis
* Day-of-week analysis
* Power BI built-in forecasting

The forecast uses historical demand patterns to estimate future transportation activity.

---

# ♿ Milestone 4 — Equity, Executive Intelligence & Advanced Analytics

Milestone 4 introduced more advanced analytical capabilities.

---

## ♿ Page 8 — Mobility Access Index & Equity

A **Mobility Access Index (MAI)** was developed to compare mobility access across locations.

The index uses components such as:

* Trip volume
* Reliability
* Route density

The page includes:

* Overall MAI Score
* Average Reliability
* Average Speed
* Total Trips
* MAI Score by Location
* Location-level comparison
* Population and trip analysis
* Conditional formatting

The original population-based Trips Per Capita component was removed after analysis showed that the available population field was not a reliable fixed population value per location.

---

# 📊 Page 9 — Executive Intelligence Dashboard

The Executive Intelligence page provides a consolidated overview of the most important mobility indicators.

It includes:

* Total Trips
* Average Speed
* Average Reliability
* Overall MAI Score
* Average Rainfall
* Trips by Mobility Segment
* Demand Trend
* Demand by Weather
* MAI Score by Location

This page is designed for users who want a quick overview without going through every individual dashboard page.

---

# 🔮🚨 Page 10 — Forecasting & Anomaly Detection

The final advanced analytics page combines demand forecasting and anomaly detection.

### Forecasting

The dashboard uses Power BI's built-in forecasting functionality to estimate future demand.

### Anomaly Detection

Anomaly detection is used to identify unusual mobility patterns.

A speed anomaly is identified by comparing segment-level speed with the overall average and standard deviation.

The dashboard provides:

* Total Trips
* Anomalies Flagged
* Average Rainfall
* Demand Forecast
* Demand Anomalies

Power BI's **Explain this anomaly** functionality can also be used to investigate possible factors such as weather, mobility segment, and location.

---

# 📈 Key Dashboard Capabilities

The completed project demonstrates:

* ✅ Data cleaning
* ✅ Data transformation
* ✅ Star-schema data modeling
* ✅ Table relationships
* ✅ DAX calculations
* ✅ KPI development
* ✅ Interactive slicers
* ✅ Mobility segmentation
* ✅ Geographic analysis
* ✅ Weather analysis
* ✅ Demand analysis
* ✅ Mobility access analysis
* ✅ Equity analysis
* ✅ Forecasting
* ✅ Anomaly detection
* ✅ Executive reporting
* ✅ Interactive Power BI visualization

---

# 💡 Key Insights

The dashboard allows users to investigate questions such as:

* Which mobility segment contributes the most trips?
* How does Ride-Hailing activity change over time?
* How is Micromobility being used across locations?
* How does weather relate to trip volume?
* Does rainfall have an observable relationship with average speed?
* Which locations have higher or lower mobility access?
* What are the historical demand trends?
* What could future demand look like?
* Which mobility patterns appear unusual?

---

# 🧠 Challenges & Solutions

During development, several data and modeling issues were identified and resolved.

### 1. Date mismatch

A mismatch between date and datetime values affected the relationship between the fact table and Date table.

**Solution:** The date structure was corrected so that time-based analysis worked properly.

### 2. Duplicate Route IDs

Duplicate route values affected the intended relationship structure.

**Solution:** Route dimension data was cleaned so that unique route values could be used for the relationship.

### 3. Population Data Limitation

The available population-related field was found to vary at trip level rather than representing a fixed population for each location.

**Solution:** The population-based Trips Per Capita component was removed from the Mobility Access Index.

### 4. Sparse Time-Series Data

Limited daily data affected some time-based analysis.

**Solution:** Monthly-level analysis and Power BI forecasting were used where appropriate.

### 5. DAX Measure Filtering

An issue occurred while calculating anomaly counts because a measure was used directly as a filter expression.

**Solution:** The calculation was rewritten using `FILTER()` so that the measure could be evaluated row by row.

---

# 📂 Repository Structure

```text
smart-urban-mobility-dashboard/
│
├── README.md
│
├── Smart_Urban_Mobility_Dashboard.pbix
│
├── screenshots/
│   ├── page1-ride-hailing.png
│   ├── page2-micromobility.png
│   ├── page3-modal-substitution.png
│   ├── page4-weather-sensitivity.png
│   ├── page5-demand-forecasting.png
│   ├── page8-mobility-access-equity.png
│   ├── page9-executive-intelligence.png
│   └── page10-forecasting-anomalies.png
│
└── docs/
    └── Project_Documentation.docx
```

---

# 🚀 Future Improvements

Possible future improvements include:

* Page navigation buttons
* Synced slicers across pages
* Location-level drill-through pages
* Dashboard performance optimization
* Consistent theme across all pages
* Scheduled data refresh
* Row-Level Security where required
* Publishing the dashboard to a Power BI workspace

---

# 🏁 Conclusion

The **Smart Urban Mobility and Traffic Intelligence Dashboard** demonstrates how Power BI can be used to transform raw mobility data into meaningful analytical insights.

The project progressed through four milestones, covering:

**Data Preparation → Data Modeling → Mobility Analytics → Geospatial Analysis → Weather Analysis → Equity Analysis → Executive Reporting → Forecasting → Anomaly Detection**

Through this project, practical experience was gained in **Power BI, Power Query, DAX, data modeling, interactive visualization, geospatial analysis, mobility segmentation, forecasting, and anomaly detection**.

---

# 📚 References

1. Microsoft Power BI Desktop
2. Microsoft Power BI Documentation
3. Microsoft DAX Documentation
4. Infosys Springboard Virtual Internship
5. Smart City Mobility Sample Dataset
6. Power BI Analytics Features
7. Project-specific Power Query transformations and DAX calculations

---

# 👩‍💻 Author

**Lahari Guggilam**

B.Tech — CSE (Data Science)

Power BI | Data Analytics | Data Science

```

**For GitHub, I recommend this version** because a recruiter can understand the complete scope of your project without opening the `.pbix` file.
```
