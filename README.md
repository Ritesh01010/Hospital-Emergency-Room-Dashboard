
-----

# Hospital Emergency Room Analysis Dashboard

## Project Overview

This project focuses on the analysis of a hospital's Emergency Room (ER) operations. The primary objective is to develop a comprehensive dashboard that provides actionable insights into patient demographics, wait times, satisfaction scores, and departmental workflows. By visualizing key performance indicators (KPIs), the dashboard aims to help hospital administrators and stakeholders monitor ER efficiency, identify bottlenecks, and make data-driven decisions to improve patient care and resource allocation.

-----

## Final Dashboard

Below is a snapshot of the final interactive dashboard.

  * *Add your final dashboard screenshot here*
    
    ![Hospital Emergency Room Dashboard](https://github.com/Ritesh01010/Hospital-Emergency-Room-Dashboard/blob/main/Dashboard.png)


-----

## Key Performance Indicators (KPIs)

The dashboard tracks the following core metrics to provide a high-level overview of the ER performance:

  * **Total Number of Patients:** A distinct count of all patients visiting the ER to measure overall patient volume.

  * **Average Patient Wait Time:** The average time (in minutes) a patient waits before being attended to, which is a critical measure of operational efficiency.

  * **Average Patient Satisfaction Score:** The average satisfaction rating provided by patients (on a scale of 1-10), reflecting the quality of care and patient experience.


-----

## Project Workflow & Screenshots

The project was executed following these key steps. Below are screenshots from each stage of the process.

### 1\. Data Cleaning & Preparation (Power Query)

The raw data was loaded into Power Query for cleaning and preparation. Key steps included correcting data types, standardizing inconsistent values in the `Patient Gender` column, removing duplicate columns, and handling blank values.

  * *Add a screenshot of the Power Query editor showing the applied steps*
    
    ![Power Query Editor](path/to/your/power_query_screenshot.png)
    

### 2\. Data Modeling & Analysis (DAX)

A **Calendar Table** was created to facilitate time-based analysis. The data model was designed to link the calendar table with the main data table. Calculated columns were created using DAX to segment and categorize data for deeper analysis.


### 3\. Dashboard Visualization

The cleaned and modeled data was visualized in an interactive dashboard using various charts and slicers to allow for dynamic data exploration.

#### **DAX Formulas**

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

## Data Analysis & Visualizations

The dashboard includes a variety of visualizations to provide insights from different perspectives.

  * **Patient by Age Group, Gender & Attend Status**

      * *Add a screenshot of these charts from your dashboard*
        
        ![Demographic and Status Charts](https://github.com/Ritesh01010/Hospital-Emergency-Room-Dashboard/blob/main/Charts.png)
        



  * **Interactive Slicers:** The dashboard includes slicers for **Year**, **Department Referral**, and **Patient Gender**, allowing users to filter the entire report.

      * *Add a screenshot of the slicers*
        
        ![Slicers](https://github.com/Ritesh01010/Hospital-Emergency-Room-Dashboard/blob/main/Slicer.png)
        

-----

## Tools Used

  
  * **Microsoft Excel:** Used for initial data review and preparation.

-----

## Conclusion & Insights

This dashboard successfully translates raw ER data into a powerful decision-making tool. Key insights that can be derived include: identifying the busiest months, understanding the primary age and gender demographics of patients, evaluating wait time performance against the 30-minute target, and determining which departments are most impacted by ER traffic. These insights enable the hospital management to optimize staffing, streamline processes, and ultimately enhance the patient experience.
