
-----

# Hospital Emergency Room Analysis Dashboard

## Project Overview

This project focuses on the analysis of a hospital's Emergency Room (ER) operations. The primary objective is to develop a comprehensive dashboard that provides actionable insights into patient demographics, wait times, satisfaction scores, and departmental workflows. By visualizing key performance indicators (KPIs), the dashboard aims to help hospital administrators and stakeholders monitor ER efficiency, identify bottlenecks, and make data-driven decisions to improve patient care and resource allocation.

##  Dashboard

-----

## Key Performance Indicators (KPIs)

The dashboard tracks the following core metrics to provide a high-level overview of the ER performance:

  * **Total Number of Patients:** A distinct count of all patients visiting the ER to measure overall patient volume.
  * **Average Patient Wait Time:** The average time (in minutes) a patient waits before being attended to, which is a critical measure of operational efficiency.
  * **Average Patient Satisfaction Score:** The average satisfaction rating provided by patients (on a scale of 1-10), reflecting the quality of care and patient experience.

-----

## Project Workflow

The project was executed following these key steps:

1.  **Data Gathering:** The primary dataset used was `Hospital Emergency Room Data.csv`, containing anonymized patient records.
2.  **Data Cleaning & Preparation (Power Query):**
      * The raw data was loaded into Power BI.
      * Data types were checked and corrected for all columns (e.g., converting dates and numerical values).
      * Inconsistencies in the `Patient Gender` column (e.g., 'M', 'F', 'Male') were standardized.
      * Removed a duplicate `Patient Admission Flag` column.
      * Handled blank values in the `Patient Satisfaction Score` column.
3.  **Data Modeling & Analysis (DAX):**
      * A **Calendar Table** was created to facilitate time-based analysis.
      * Calculated columns were created using DAX to segment and categorize data:
          * **Age Group:** Patients were grouped into logical age brackets for demographic analysis.
          * **Patient Attend Status:** Patients were categorized as "Within Time" or "Delay" based on whether their wait time was less than 30 minutes.
4.  **Dashboard Visualization:** The cleaned and modeled data was visualized in an interactive dashboard using various charts and slicers to allow for dynamic data exploration.

-----

## Tools Used

  * **Microsoft Power BI:** The primary tool for data modeling, analysis (DAX), and dashboard visualization.
  * **Microsoft Excel:** Used for initial data review and preparation.

-----

## Data Analysis & Visualizations

The dashboard includes a variety of visualizations to provide insights from different perspectives:

  * **Patient by Gender & Patient Attend Status (Donut Charts):** Provide a quick percentage breakdown of the patient population by gender and their wait time status (Delay vs. Within Time).
  * **Patient by Age Group (Bar Chart):** Displays the distribution of patients across different age groups, helping to identify the most frequent age demographics visiting the ER.
  * **Department Referral (Treemap):** Shows the distribution of patients referred to different hospital departments, highlighting which departments receive the most ER referrals.
  * **No. of Patients by Month & Year (Area Chart):** Visualizes trends in patient volume over time, helping to spot seasonal patterns or periods of high activity.
  * **Interactive Slicers:** The dashboard includes slicers for **Year**, **Department Referral**, and **Patient Gender**, allowing users to filter the entire report and drill down into specific data segments.

### DAX Formulas

Below are the key DAX formulas used to create new analytical columns:

1.  **Age Group Creation:**

    ```dax
    Age Group =
    IF([Patient Age] >= 70, "70-79",
        IF([Patient Age] >= 60, "60-69",
            IF([Patient Age] >= 45, "45-59",
                IF([Patient Age] >= 30, "30-44",
                    IF([Patient Age] >= 15, "15-29",
                        IF([Patient Age] >= 5, "05-14", "0-4")
                    )
                )
            )
        )
    )
    ```

2.  **Patient Attend Status:**

    ```dax
    Patient Attend Status =
    IF([Patient Waittime] < 30, "Within Time", "Delay")
    ```

-----

## Conclusion & Insights

This dashboard successfully translates raw ER data into a powerful decision-making tool. Key insights that can be derived include: identifying the busiest months, understanding the primary age and gender demographics of patients, evaluating wait time performance against the 30-minute target, and determining which departments are most impacted by ER traffic. These insights enable the hospital management to optimize staffing, streamline processes, and ultimately enhance the patient experience.
