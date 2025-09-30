# ✈️ Airline-Delay-Cause-Dashboard
This Tableau project analyzes U.S. airline flight delays using public Kaggle data. The dashboard highlights delay causes, airline performance, airport impacts, and time-based trends, giving stakeholders clear insights into why delays happen, where they occur most, and which airlines or airports contribute the most.


[![Made with Tableau Public](https://img.shields.io/badge/Made%20with-Tableau%20Public-blue?logo=tableau)](https://public.tableau.com/app/profile/ogheneochuko.ogidiagba/viz/AirlineDelayCause_17590191912560/AirlineDelayCause)
[![Dataset: Kaggle](https://img.shields.io/badge/Dataset-Kaggle-orange)](https://www.kaggle.com/datasets/sriharshaeedala/airline-delay?resource=download)
![Status](https://img.shields.io/badge/Status-Completed-success)

---

## 📂 Repository Structure
Airline-Delay-Dashboard/
│── README.md   ← Main repo README (overview of the whole project)
│
├── Dashboard/
│   ├── README.md   ← Detailed documentation for this Tableau dashboard
│   └── Dashboard Screenshot.png
│
├── Data/
│   └── Airline_Delay_Cause.csv
│
└── Tableau Files/
    └── Airline_Delay_Dashboard.twbx

---

## 1. Introduction

This project analyzes airline flight delays using Tableau. The dashboard highlights the main causes of delays, airline performance, airport impacts, and overall delay trends over time.

**Purpose:**

- To identify which factors contribute most to delays.  
- To compare airlines and airports by delay patterns.  
- To give stakeholders a clear picture of delay behavior for decision-making.  

**Disclaimer:**  
This project is based on a public dataset and is for learning and demonstration purposes only. It does not represent any specific airline, airport, or government institution.

---

## 2. Problem Statement

The analysis seeks to answer the following key questions:

- What are the main causes of flight delays?  
- Which airlines contribute the most to delays?  
- Which airports experience the highest delays?  
- How do delays vary across time (year, month, season)?  

---

## 3. Skills Demonstrated

This project showcases the following Tableau concepts:

- Pivoting & calculated fields  
- KPI cards for high-level metrics  
- Dual-axis chart trick (donut visualization)  
- Interactive filters & actions (slicers)  
- Maps with geographic hierarchies  
- Dashboard design with custom background  

---

## 4. 📂 Dataset  
- **Source**: [![Kaggle Dataset](https://img.shields.io/badge/Kaggle-Airline%20Delay%20Dataset-blue)](https://www.kaggle.com/datasets/sriharshaeedala/airline-delay?resource=download)

This dataset contains U.S. airline flight delay records, including flight counts, delay minutes, and categorized delay causes. It was published on Kaggle by **Sriharsha Eedala**.
- **Main fields used**:  
  - `arr_del15` → Number of delayed flights  
  - `arr_flights` → Total flights  
  - `month` → Month of operation (converted from numeric to month name)  
  - `carrier` → Airline code  
  - `airport` → Airport code

---

## 5. Data Transformation

Data preparation steps included:

- Pivoting delay cause columns into a single field.  
- Creating calculated fields,  
- Percentage of Delayed Flights
  ```text
  % Delayed Flights = SUM([arr_del15]) / SUM([arr_flights])

- Month Name (from numeric month)
  ```text
  Month Name = DATENAME('month', MAKEDATE(2000, [Month], 1))

- Year (from Year-Month Date field)
  ```text
  Year = YEAR([Year-Month Date])

- Converting numeric months to proper month names using calculated field:
  ```text
  CASE [Month]
  WHEN 1 THEN "January"
  WHEN 2 THEN "February"
  WHEN 3 THEN "March"
  WHEN 4 THEN "April"
  WHEN 5 THEN "May"
  WHEN 6 THEN "June"
  WHEN 7 THEN "July"
  WHEN 8 THEN "August"
  WHEN 9 THEN "September"
  WHEN 10 THEN "October"
  WHEN 11 THEN "November"
  WHEN 12 THEN "December"
  END

- Creating a Month Name field from Month:
  ```text
  YEAR([Year-Month Date])

- Applying Top N filter for airline analysis (Top 10).


---

## 6. Modeling

Since the dataset is flat, Tableau relationships were minimal. Key modeling included:

- Creating hierarchies (Year → Month → Date).

- Aggregations using calculated fields.

- KPIs combining flight totals and delays.

---

## 7. Analysis & Visualizations

- The dashboard consists of several visual components:

**KPI Cards**

- Total Flights

- Delayed Flights

- % of Flights Delayed

- Total Delay Minutes


**Delay Trends Over Time (Line Chart)**

- Tracks arrival delays across years.


**Delays by Airline (Stacked Bar, Top 10)**

- Compares carriers by total delays, color-coded by cause.


**Delays by Airport (Map)**

- Shows which airports experience the highest delays geographically.


**Donut Chart – Delay Causes Breakdown**

- Displays the percentage share of each delay factor.


**Delay Minutes by Cause (Bar Chart)**

- Highlights which causes drive the largest cumulative delay minutes.


📸 **Dashboard Preview:**
```markdown
![Dashboard Screenshot](Dashboard/Dashboard%20Screenshot.png)


---

## 8. Conclusion & Recommendations

**Insights:**

- Late Aircraft and Carrier delays account for the largest share of delay minutes.

- Weather delays are significant but less dominant compared to operational causes.

- Certain airlines (e.g., Southwest, American, Delta) consistently show higher delays.

- Delay trends peak in some years (2018–2019) and drop during events like 2020.


**Recommendations:**

- Airlines should focus on improving turnaround efficiency (Late Aircraft).

- Better carrier resource planning may reduce operational delays.

- Seasonal and weather-prone airports require proactive scheduling strategies.



---
