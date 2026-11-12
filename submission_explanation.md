# Short submission explanation

**Theme:** Campus energy consumption

**Intended users:** Campus administrators and facility managers.

**KPIs**
1. Total energy consumption (kWh): shows the total electricity used across the selected buildings and date range.
2. Average daily consumption (kWh): provides a typical daily usage baseline for comparing periods.
3. Peak recorded demand (kW): identifies the highest observed demand and helps highlight periods that may need operational attention.

**Visualizations**
1. Line chart: daily energy consumption trend.
2. Bar chart: total consumption by building.
3. Bar chart: average demand by hour of day.

**Interactive filter:** Users can select a date range and one or more buildings. KPI cards and charts update to reflect the selected records.

**Data update demonstration:** The dashboard includes a form to add a new simulated reading. The record is saved to the CSV dataset and the dashboard reruns to display the updated values.

**Actionable finding:** In this simulated dataset, the Hostel Block has the highest overall consumption. Campus facility staff could investigate its evening usage pattern and review whether lighting, cooling, or other loads can be scheduled more efficiently. This is a hypothesis for investigation, not proof of waste.

**Limitations:** All readings are simulated. The dashboard is not connected to physical meters. The anomaly rule is a simple statistical flag and should not be treated as a confirmed equipment fault.
