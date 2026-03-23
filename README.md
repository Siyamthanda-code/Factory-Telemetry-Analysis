# Daikibo Factory Telemetry Analysis 📊

## Project Overview

This project focuses on analyzing telemetry data for **Daikibo**, a global manufacturing client. The objective was to process one month of high-frequency machine data (May 2021) to identify operational bottlenecks and answer two key business questions:

1.  Which factory location experienced the most machine downtime?
2.  Which specific machine types were responsible for the downtime in those locations?

## Data Source

The dataset (`daikibo-telemetry-data.json`) contains telemetry streams from 4 global factories:

-   **Daikibo Factory Meiyo** (Tokyo, Japan)
-   **Daikibo Factory Seiko** (Osaka, Japan)
-   **Daikibo Berlin** (Berlin, Germany)
-   **Daikibo Shenzhen** (Shenzhen, China)

Each location operates 9 types of machines, reporting status updates every 10 minutes.

**Note:** The raw JSON data file exceeds 25MB and is not included in this repository.

## Tools & Technologies

-   **Tableau Desktop:** Data visualization and business intelligence.
-   **Data Format:** JSON (Nested structure).

## Methodology

### 1\. Data Preparation

The nested JSON data was imported into Tableau. To translate status messages into actionable metrics, a calculated field was created:

-   **Calculated Field:** `Unhealthy`
-   **Logic:** Value of `10` assigned to every "unhealthy" status.
-   **Reasoning:** Since machines report every 10 minutes, a single unhealthy status point equates to 10 minutes of potential downtime.

### 2\. Visualization

Two primary views were developed to analyze the data:

-   **Down Time per Factory:** A bar chart aggregating total downtime by factory location to identify problem areas.
-   **Down Time per Device Type:** A bar chart breaking down downtime by specific machinery across the company.

### 3\. Dashboard Interactivity

A unified dashboard was constructed linking the two visualizations. The "Down Time per Factory" chart acts as a global filter:

-   _Action:_ Selecting a specific factory bar filters the "Device Type" view.
-   _Insight:_ This allows for immediate drill-down analysis, instantly revealing which machines are failing within a specific selected location.

## Key Findings

-   The dashboard successfully highlights the geographic location with the highest aggregate downtime.
-   By utilizing the dashboard filter, specific device types responsible for the majority of failures in those locations can be isolated for maintenance prioritization.
