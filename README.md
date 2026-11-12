# Exploratory-Data-Analysis 

This repository contains an exploratory data analysis (EDA) project—completed as part of a **Module End Evaluation**—focusing on a comprehensive healthcare dataset comprising medical examinations, hospitalization details, and customer profiles. Along with this attaching the data set that have been provided.


### Dataset Overview
This dataset consist of :


## Healthcare Data Analysis and Insights::

The healthcare industry generates vast amounts of data daily, providing valuable insights for healthcare providers and policymakers to improve patient care, allocate resources effectively, and manage healthcare costs. This project aims to analyze a comprehensive healthcare dataset comprising medical examinations, hospitalization details, and customer profiles to extract insights into patient health profiles, medical histories, and healthcare costs. By exploring relationships between various health metrics, identifying trends, and visualizing key patterns, we aim to deliver actionable insights to healthcare stakeholders for informed decision-making through rigorous data cleaning, transformation, exploration, and anal




## Data Pre-processing

 The following steps were executed:

 Q1.  * Scanned all columns across both the **“Medical Examinations”** and **“Hospitalization Details”** tables to detect and quantify missing entries explicitly marked with question marks (`?`).

Q2.    **Month:** Replaced all missing entries in the `month` column with the default value **"Sep"**.
        **Year:** Filled missing values in the `year` column by calculating the overall average of the existing valid year entries and rounding the  result to the nearest integer.

Q3. *Identified the most frequently occurring values (mode) for the **`smoker`**, **`Hospital tier`**, and **`City tier`** columns.
   * Imputed missing entries within these columns with their respective modes to preserve the dataset's underlying distributional characteristics.

Q4.   * Inspected the `State ID` column for missing or null records.
   * Filled any unassigned or missing state values with **"Unknown"** to maintain row count consistency and flag unrecorded geographical entries for downstream analysis.
