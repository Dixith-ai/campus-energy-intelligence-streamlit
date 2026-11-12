<div align="center">

# CAMPUS ENERGY INTELLIGENCE

**Understand campus energy. Find the patterns. Investigate what matters.**

<br>

[![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=flat-square&logo=python&logoColor=white)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-App-FF4B4B?style=flat-square&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![Plotly](https://img.shields.io/badge/Plotly-Visualizations-3F4F75?style=flat-square&logo=plotly&logoColor=white)](https://plotly.com/python/)
![Dataset](https://img.shields.io/badge/Dataset-Simulated-168B70?style=flat-square)
![Status](https://img.shields.io/badge/Project-Academic%20Prototype-526477?style=flat-square)

<br>

*A campus energy monitoring and analytics dashboard built with Python, Streamlit and Plotly.*

</div>

---

## Overview

Campus Energy Intelligence is an interactive dashboard for exploring electricity consumption across campus buildings. It brings operational indicators, time-based analysis, building comparisons and data-quality information into one interface.

The project is designed around three practical questions:

- **Where** is electricity being consumed?
- **When** does demand rise or fall?
- **What** should campus facilities staff investigate?

The dashboard also includes a simulated meter-reading workflow. New records can be added to the dataset, after which the KPIs and visualizations recalculate.

> [!IMPORTANT]
> **This project uses simulated data.** It is an academic demonstration, not a live campus monitoring system. It is not connected to physical meters, a building management system or a utility provider. All readings and findings are illustrative.

## Dashboard at a glance

| Indicator | What it communicates |
|:--|:--|
| **Total energy** | Energy consumed in the selected reporting window, in kWh |
| **Daily average** | Mean daily consumption across complete days only |
| **Peak demand** | Highest recorded demand in the selected window, in kW |
| **Active buildings** | Number of selected buildings represented in the filtered data |

The dashboard supports date-range and building filters. KPI cards, charts and findings respond to the selected view.

## Visual analysis

Each visualization is selected for a specific analytical purpose.

| Visualization | Purpose |
|:--|:--|
| **Consumption trajectory** | Tracks daily energy consumption and distinguishes complete from incomplete days |
| **Building energy mix** | Compares each building's share of selected-period consumption |
| **Demand intensity heatmap** | Shows observed demand by date and hour, with partial and missing days identified |
| **Consumption treemap** | Shows the relative scale of energy use across buildings |
| **Peak demand gauge** | Highlights the highest recorded demand |
| **Energy-demand scatter plot** | Explores the relationship between interval energy and recorded demand |
| **Typical hourly demand** | Compares hourly demand using complete days only |
| **Operational findings** | Presents a data-supported observation for further investigation |

## Data integrity

A dashboard should make the quality and limitations of its data visible, not hide them.

### Completeness rule

A day is considered complete when **every selected building has readings in 24 distinct hourly slots**.

- Multiple readings within the same hour count as one slot for completeness.
- Partial-day readings remain visible in the consumption trend and heatmap.
- Days with no observations are identified separately from partial days.
- Incomplete days are excluded from the daily average and typical hourly demand profile.
- Data coverage is calculated from distinct hourly slots, capped at 24 per selected building per day.

### Data validation

The application performs basic checks when loading the CSV dataset:

- Timestamp parsing and numeric conversion.
- Removal of rows with missing required values.
- Duplicate handling for building-and-timestamp records.
- Rejection of negative energy and demand values.
- Retention of record status to distinguish ordinary simulated readings from manually added demonstration records.

### Anomaly screening

Unusual readings are screened using a building-and-hour median/MAD baseline with a minimum lift threshold.

A flagged reading is a prompt for investigation. It is not proof of equipment failure, energy waste or a safety issue.

## Technology

| Technology | Role |
|:--|:--|
| [Python](https://www.python.org/) | Application logic and calculations |
| [Streamlit](https://streamlit.io/) | Interactive dashboard interface |
| [Pandas](https://pandas.pydata.org/) | Data loading, filtering, grouping and validation |
| [NumPy](https://numpy.org/) | Numerical and statistical operations |
| [Plotly](https://plotly.com/python/) | Interactive data visualizations |
| CSV | Portable demonstration data storage |

## Run locally

### Requirements

- Python 3.10 or later
- pip
- The project files and CSV dataset

### Project structure

```text
campus_energy_dashboard_v2/
│
├── app.py
├── requirements.txt
├── README.md
│
└── data/
    └── energy_readings.csv
```

### Installation

**1. Open a terminal in the project directory.**

**2. Install the dependencies.**

```bash
pip install -r requirements.txt
```

**3. Launch the dashboard.**

```bash
streamlit run app.py
```

**4. Open the local address printed by Streamlit.**

```text
http://localhost:8501
```

## Demonstrate a data update

The dashboard includes a simulated meter-reading form.

1. Expand **Add a new simulated meter reading**.
2. Select a campus building.
3. Enter energy consumed in kWh and demand in kW.
4. Choose the reading date and time.
5. Select **Save reading and refresh dashboard**.

The new record is written to `data/energy_readings.csv`. The application reloads the dataset and recalculates the dashboard.

> [!NOTE]
> The update workflow writes to a local CSV file. It demonstrates a data update; it is not a live meter feed, cloud database or concurrent multi-user ingestion service.

## Understanding the findings

The dashboard identifies the building with the largest share of energy consumption in the current selection. This can help facilities staff decide where to review operating schedules and major electrical loads.

A higher consumption share does not automatically mean a building is inefficient. Building size, operating hours and equipment mix all affect energy demand. Context is required before recommending corrective action.

## Limitations

- All readings are synthetic and do not represent measured campus consumption.
- The dashboard is not connected to smart meters, IoT devices, building management systems or utility APIs.
- Hourly completeness assumes 24 expected reading slots per building per day.
- Local CSV storage is appropriate for a classroom demonstration, not concurrent production ingestion.
- Statistical anomaly flags require human review and are not confirmed faults.
- Findings depend on the selected reporting period, selected buildings and quality of the supplied records.

## Project objective

This project demonstrates how a campus-related activity can be monitored through key performance indicators, interactive visualizations, filters and a data-update workflow.

It serves as an educational prototype for exploring energy consumption and supporting evidence-based campus operations.

---

<div align="center">

**CAMPUS ENERGY INTELLIGENCE**

*Measure the load. Understand the pattern.*

<sub>Academic prototype · Interactive analytics · Simulated campus energy dataset</sub>

</div>
