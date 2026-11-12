# Exploratory-Data-Analysis 

This repository contains an exploratory data analysis (EDA) project—completed as part of a **Module End Evaluation**—focusing on a comprehensive healthcare dataset comprising medical examinations, hospitalization details, and customer profiles. Along with this attaching the data set that have been provided.


### Dataset Overview
This dataset consist of :

   *Customer Information & Metrics:* **`Customer ID`**, **`First Name`**, **`Age`**, **`Date of Birth`**, **`State ID`**
   
   *Health & Clinical Indicators:* **`BMI`**, **`HBA1C`**, **`Heart Issues`**, **`Any Transplants`**, **`Cancer history`**, **`NumberOfMajorSurgeries`**, **`smoker`**, **`Weight Status`**, **`Diabetes Status`**
   
   *Hospital & Financial Details:* **`charges`**, **`Hospital tier`**, **`City tier`**


## Healthcare Data Analysis and Insights::

The healthcare industry generates vast amounts of data daily, providing valuable insights for healthcare providers and policymakers to improve patient care, allocate resources effectively, and manage healthcare costs. This project aims to analyze a comprehensive healthcare dataset comprising medical examinations, hospitalization details, and customer profiles to extract insights into patient health profiles, medical histories, and healthcare costs. By exploring relationships between various health metrics, identifying trends, and visualizing key patterns, we aim to deliver actionable insights to healthcare stakeholders for informed decision-making through rigorous data cleaning, transformation, exploration, and anal




## Data Pre-processing

 The following steps were executed:
 
 ### Data Cleaning

 Q1.  * Scanned all columns across both the **“Medical Examinations”** and **“Hospitalization Details”** tables to detect and quantify missing entries explicitly marked with question marks (`?`).

Q2.    * Month: Replaced all missing entries in the `month` column with the default value **"Sep"**.
       
       * Year: Filled missing values in the `year` column by calculating the overall average .
        
       * Implemented using  IF and ISBLANK Function.

Q3. *Identified the most frequently occurring values (mode) for the **`smoker`**, **`Hospital tier`**, and **`City tier`** columns.
    * Imputed missing entries within these columns with their respective modes to preserve the dataset's underlying distributional characteristics.

Q4.   * Inspected the `State ID` column for missing or null records.
      * Filled any unassigned or missing state values with **"Unknown"** using IF and ISBLANK Function.



### Data Transformation

The following steps and transformations were applied to clean, parse, and enrich the dataset columns across the different tables:

Q1. **Split 'names' Column (`Customer Names` Table)**
   *  Split the combined `names` column into 3 distinct and meaningful columns: **`Title`**, **`First Name`**, and **`Last Name`**.
   *  Used LEFT and RIGHT Functions.

Q2. **Convert "NumberOfMajorSurgeries" (`Medical Examinations` Table)**
   *  Converted the text-formatted `NumberOfMajorSurgeries` column into proper numerical using  (0).
   * Done using Find and Replace Function.

Q3. **Check Inconsistencies in 'Heart Issues' and 'smoker' Columns**

   * * Standardize all values uniformly into clean YES and NO.

Q4. **Create "Weight Status" Column (BMI Categorization)**
   *  Created a new calculated column named **`Weight Status`** based on the patient's BMI values using the following thresholds:
     * **Below 18.5:** Underweight
     * **18.5 – 24.9:** Normal Weight
     * **25.0 – 29.9:** Overweight
     * **30.0 and Above:** Obesity

Q5. **Create "Diabetes Status" Column (HbA1C Categorization)**
   * Created a new calculated column named **`Diabetes Status`** categorized according to HbA1C levels:
     * **Below 5.7:** Normal
     * **5.7 – 6.4:** Prediabetes
     * **6.5 and Above:** Diabetes

Q6. **Merge Date Components (`Hospitalization Details` Table)**
   *  Merged the separate `year`, `month`, and `date` columns into a single column named **`Date of Birth`**.
   *  Using the CONCATENATE Function.
   *  Formatted the merged column using the custom date format **`DD-MMM-YYYY`**.

Q7. **Calculate Customer 'Age'**
   *  Calculated the **`Age`** of each customer using their `Date of Birth` relative to the official dataset collection date: **8th June 2023** (`2023-06-08`).
   *  Using DATEDIF Function.

Q8. **Format 'charges' Column**
   *  Formatted the financial **`charges`** column explicitly as currency displaying the dollar sign (**$**).


   ### Data Exploration, Analysis & Visualization

To prepare the dataset for comprehensive exploration, analysis, and dashboard visualization, the following consolidation and feature steps were executed:

Q1. **Master Sheet Creation ("Healthcare")**
    * Created a new consolidated sheet named **`Healthcare`**.
   *  Combined all three tables into a single unified table using **`Customer ID`** as the common primary key via **`VLOOKUP`**.

Q2. **Column Retention**
   *  Retained only the essential fields necessary for downstream insights and dashboard filtering:
     * *Customer Information & Metrics:* **`Customer ID`**, **`First Name`**, **`Age`**, **`Date of Birth`**, **`State ID`**
     * *Health & Clinical Indicators:* **`BMI`**, **`HBA1C`**, **`Heart Issues`**, **`Any Transplants`**, **`Cancer history`**,  **`NumberOfMajorSurgeries`**, **`smoker`**, **`Weight Status`**, **`Diabetes Status`**
     * *Hospital & Financial Details:* **`charges`**, **`Hospital tier`**, **`City tier`**

 

### Analysis & Visualization Roadmap

Pivot tables, custom charts, and an interactive dashboard are built to address the following key business and clinical objectives:

#### 1. PIE AND DONUT CHART
* **Cancer History:** Analyze the distribution of cancer history among smokers vs. non-smokers.
* **Transplant Impact:** Compare total major surgeries and average HbA1C differences between patients with and without a history of organ transplants

##### 2.COLUMN AND BAR CHART
* **Charges by Health Status:** Evaluate how healthcare charges vary across different **Weight Status** and **Diabetes Status** groups.
* **Hospital Tier & State ID:** Compare average charges across each **Hospital tier** within different **State IDs**.

#### 3. LINE AND SCATTER CHART
* **Age vs. BMI AND HBA1C** Explore potential correlations between age and both BMI and HbA1C levels.
* **Age vs. Charges:** Analyze the direct relationship between patient age and overall healthcare charges.

#### 4. Interactive Dashboard & Slicers
* **Consolidated Views:** Built an interactive dashboard synthesizing all primary charts with clean visual hierarchy.
* **Global Slicers:** Implemented active slicers for **`Weight Status`** and **`Diabetes Status`** to enable seamless cross-filtering across all visualizations simultaneously.
