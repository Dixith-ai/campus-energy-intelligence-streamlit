::: {align="center"}
# ⚡ Campus Energy Intelligence

### A data-driven view of campus electricity consumption.

Monitor energy usage, compare buildings, identify demand patterns, and
investigate unusual readings through an interactive analytics dashboard.

`<br>`{=html}

![Python](https://img.shields.io/badge/Python-3.10%2B-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Streamlit](https://img.shields.io/badge/Streamlit-Dashboard-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)
![Plotly](https://img.shields.io/badge/Plotly-Interactive%20Charts-3F4F75?style=for-the-badge&logo=plotly&logoColor=white)
![Data](https://img.shields.io/badge/Dataset-Simulated-16A085?style=for-the-badge)

`<br>`{=html}

**Campus Facilities · Energy Performance · Decision Support**
:::

------------------------------------------------------------------------

## ✦ Overview

Campus Energy Intelligence is an interactive dashboard designed to help
campus facility teams understand how electricity is consumed across
different buildings and time periods.

The dashboard brings key indicators, interactive visualizations,
data-quality checks, and a simulated meter-reading workflow into one
place.

> **Data notice:** This project uses synthetic, simulated readings for
> demonstration. It is not connected to physical campus electricity
> meters and must not be interpreted as live operational reporting.

## ◈ Dashboard capabilities

  -----------------------------------------------------------------------
  Capability                          What it shows
  ----------------------------------- -----------------------------------
  **Energy overview**                 Total consumption, average daily
                                      consumption, peak demand, and
                                      active buildings

  **Building comparison**             How energy consumption is
                                      distributed across campus buildings

  **Time-based analysis**             Daily consumption trends and hourly
                                      demand behaviour

  **Demand intensity**                A day-by-hour heatmap that retains
                                      observed readings and identifies
                                      partial or missing days

  **Consumption hierarchy**           A treemap showing the relative
                                      contribution of each building

  **Peak demand**                     A gauge highlighting the highest
                                      recorded demand

  **Relationship analysis**           A scatter plot comparing energy
                                      consumed with recorded demand

  **Operational findings**            A data-supported observation to
                                      guide further investigation

  **Data update demonstration**       Add a simulated meter reading and
                                      refresh the dashboard calculations
  -----------------------------------------------------------------------

## ◇ Key performance indicators

The dashboard presents four headline indicators:

1.  **Total energy consumption (kWh)**\
    Sum of the energy readings in the selected reporting window.

2.  **Average daily consumption (kWh)**\
    Mean daily energy consumption across complete days only.

3.  **Peak recorded demand (kW)**\
    Highest demand value recorded in the selected reporting window.

4.  **Active buildings**\
    Number of selected buildings represented in the filtered data.

### Data completeness

A day is considered complete when every selected building has readings
in **24 distinct hourly slots**.

-   Repeated readings within the same hour count as one hourly slot for
    completeness.
-   Partial days remain visible in the trend and heatmap.
-   Incomplete days are excluded from the daily average and recurring
    hourly demand profile.
-   Data coverage is calculated from distinct hourly slots, capped at 24
    per selected building per day.

## ▦ Visualizations

The dashboard uses different chart types for different analytical tasks.

  -----------------------------------------------------------------------
  Visualization                       Purpose
  ----------------------------------- -----------------------------------
  Area chart                          Track daily energy consumption over
                                      time

  Donut chart                         Compare each building's share of
                                      total consumption

  Heatmap                             Explore demand intensity by date
                                      and hour

  Treemap                             Understand the relative scale of
                                      building consumption

  Gauge                               Highlight the highest recorded
                                      demand

  Scatter plot                        Explore the relationship between
                                      energy and demand

  Hourly profile                      Compare typical demand by hour
                                      using complete days only
  -----------------------------------------------------------------------

## ⚙️ Technology stack

-   **Python** --- data processing and application logic
-   **Streamlit** --- interactive dashboard interface
-   **Pandas** --- dataset loading, filtering, aggregation, and
    validation
-   **NumPy** --- numerical calculations and statistical operations
-   **Plotly** --- interactive charts and visual analytics
-   **CSV** --- simple, inspectable dataset storage

## 🚀 Run locally

### 1. Prerequisites

Install Python 3.10 or later. Confirm that Python and pip are available:

``` bash
python --version
pip --version
```

### 2. Get the project

Clone the repository or download and extract the project folder.

Make sure the project retains this structure:

``` text
campus_energy_dashboard_v2/
│
├── app.py
├── requirements.txt
│
└── data/
    └── energy_readings.csv
```

### 3. Install dependencies

Open a terminal in the project folder and run:

``` bash
pip install -r requirements.txt
```

### 4. Launch the dashboard

``` bash
streamlit run app.py
```

Streamlit will provide a local URL, usually:

``` text
http://localhost:8501
```

Open that address in your browser.

## ↻ Demonstrate a data update

The dashboard includes a simulated meter-reading form.

1.  Open **Add a new simulated meter reading**.
2.  Select a campus building.
3.  Enter energy consumed in kWh and demand in kW.
4.  Choose the reading date and time.
5.  Select **Save reading and refresh dashboard**.

The new record is written to `data/energy_readings.csv`. The application
reloads the dataset and recalculates the dashboard.

**Important:** The update mechanism modifies the local CSV file. It is a
demonstration workflow, not a live meter integration or a multi-user
production data pipeline.

## ◉ Data structure

The CSV dataset uses the following fields:

  -----------------------------------------------------------------------
  Field                               Description
  ----------------------------------- -----------------------------------
  `timestamp`                         Date and time of the reading

  `building`                          Campus building associated with the
                                      reading

  `energy_kwh`                        Energy consumed, in kilowatt-hours

  `demand_kw`                         Recorded demand, in kilowatts

  `data_status`                       Indicates whether a record is
                                      simulated or manually added
  -----------------------------------------------------------------------

The application performs basic data checks, including timestamp parsing,
numeric conversion, missing-value removal, duplicate handling, and
non-negative value checks.

## ◇ Example analytical finding

The dashboard identifies the building with the highest share of energy
consumption in the selected reporting window.

This finding can help facilities staff decide where to investigate
operating schedules and major electrical loads. A higher consumption
share is a reason to investigate, not proof of energy waste.

## ⚠️ Limitations

-   All readings are simulated and do not represent actual campus
    electricity consumption.
-   The dashboard is not connected to smart meters, building management
    systems, or utility APIs.
-   The local CSV file is suitable for a classroom demonstration, not
    concurrent production use.
-   Completeness assumes an hourly reading schedule for each selected
    building.
-   Statistical anomaly flags are screening indicators, not confirmed
    equipment faults.
-   Findings depend on the selected date range, buildings, and quality
    of the supplied data.

## 🎓 Project objective

This project demonstrates how a campus-related activity can be monitored
through key performance indicators, interactive visualizations, filters,
and a data-update workflow.

It is intended as an educational prototype for exploring energy
consumption and supporting evidence-based campus operations.

------------------------------------------------------------------------

::: {align="center"}
**CAMPUS ENERGY INTELLIGENCE**

*Measure · Compare · Understand · Investigate*

`<sub>`{=html}Built as an academic dashboard project using simulated
campus energy data.`</sub>`{=html}
:::
