# Hospital Patient Analytics Dashboard (Power BI)

An interactive Power BI dashboard analyzing patient visits, demographics, and department workload for a clinic, built from patient admission records, doctor records, and a date/calendar table.

<img width="1899" height="769" alt="image" src="https://github.com/user-attachments/assets/43c291e7-f894-43a6-8fb5-b91d9a9eab78" />


## 📊 Business Problem

Clinic administrators need a quick, visual way to answer:
- How many patients are being seen, and how is that trending over time?
- Which departments and doctors are carrying the most patient load?
- What does the patient population look like (age, gender)?
- How efficiently are beds being used (bed nights, inpatient %)?

This dashboard consolidates raw patient, doctor, and calendar data into a single interactive view that answers these questions without manual reporting.

## 🔑 Key Insights

- **Patient volume by date** reveals day-to-day demand fluctuations, useful for staffing and resource planning.
- **Neurology and General Physician** are the highest-volume departments, followed by Psychiatry and Cardiology — helpful for identifying where additional staffing or resources may be needed.
- **Gender split** is close to even (55% M / 44% F), with a small unknown/other segment worth investigating for data quality.
- **Age distribution** peaks in the 40–60 range, showing the clinic's core patient demographic skews toward middle-aged and older adults.
- **Inpatient percentage (IP%)** and **Days of Active Patient (DAP)** vary significantly by doctor, which can highlight differences in case complexity or admission patterns across providers.

## 🛠️ Tools & Techniques Used

- **Power BI Desktop** — data modeling, DAX measures, report design
- **Power Query** — data cleaning and transformation (splitting/joining, calculated columns)
- **DAX Measures**, including:
  - Aggregate KPIs: Patient Count, Bed Nights, Average Age, DAP, IP%
  - Time-intelligence patterns using a dedicated calendar table
  - Row-level calculated columns (e.g., age from DOB, stay length from In_Date/Out_Date)
- **Data Modeling** — star-schema style relationships between `patients`, `doctors`, and `calendar` tables, joined via `Doctor_ID` and `Date`
- **Slicers & cross-filtering** for interactive drill-down across all visuals

## 🗂️ Data Sources

| File | Description | Rows |
|---|---|---|
| `patients.csv` | Patient-level records: demographics, admission/discharge dates, referring doctor | ~4,200 |
| `doctors.csv` | Doctor directory: name, department, ID | 35 |
| `calendar.csv` | Standalone date table for time-based filtering and analysis | 62 days |

*Note: Patient data is synthetic/sample data used for demonstration purposes only — no real patient information is included.*

## 📁 Repository Contents

```
├── Hospital_Dashbord.pbix     # Power BI report file
├── patients.csv               # Patient records (sample data)
├── doctors.csv                # Doctor directory
├── calendar.csv               # Date dimension table
└── README.md                  # Project overview (this file)
```

## 🚀 How to View

1. Download `Hospital_Dashbord.pbix`
2. Open in [Power BI Desktop](https://powerbi.microsoft.com/desktop/) (free)
3. All data is embedded in the file — no additional setup needed to explore

## 📈 Dashboard Features

- **KPI cards**: Patient Count, Bed Nights, Average Age, DAP, IP%
- **Patient Count by Date** — trend line for demand over time
- **Patient Count by Gender** — donut breakdown
- **Patient Count by Department** — bar chart of departmental load
- **Patient Count by Age (bins)** — histogram of patient age distribution
- **Doctor-level detail table** — per-doctor patient count, IP%, and DAP

---
*Built as a data analytics portfolio project to demonstrate Power BI dashboard design, DAX, and data modeling skills.*
