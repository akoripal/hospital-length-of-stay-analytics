# Hospital Utilization & Prolonged Stay Risk Analytics

## Overview

Hospital systems continuously monitor inpatient utilization to improve operational efficiency, reduce readmissions, and manage patient complexity. One of the most important operational metrics in hospital management is **Length of Stay (LOS)**. Prolonged hospitalizations increase operational costs, reduce bed availability, and may indicate underlying clinical or care coordination challenges.

This project analyzes **101,766 inpatient encounters involving diabetes patients** to identify drivers of prolonged hospital stays and predict high-risk patients using machine learning.

The project implements an **end-to-end healthcare analytics workflow**, integrating cloud data warehousing, predictive modeling, and interactive business intelligence dashboards.

The final dashboard enables exploration of:

* inpatient utilization patterns
* drivers of hospital length of stay
* readmission trends
* clinical complexity indicators
* predicted prolonged stay risk segments

---

# Project Architecture

The analytics pipeline follows a modern healthcare analytics workflow:

```
Raw Clinical Dataset
        ↓
Data Cleaning & Feature Engineering (Python / SQL)
        ↓
BigQuery Cloud Data Warehouse
        ↓
Machine Learning Model (Logistic Regression)
        ↓
Risk Prediction Dataset
        ↓
Interactive Qlik Sense Dashboard
```

This architecture mirrors typical analytics environments used by **hospital operations teams, population health analysts, and healthcare BI teams**.

---

# Dataset

The dataset contains **101,766 hospital encounters** with demographic, clinical, and utilization attributes associated with inpatient diabetes care.

### Patient Demographics

* Age group
* Race
* Gender

### Hospital Utilization

* Time in hospital
* Number of outpatient visits
* Number of emergency visits
* Number of prior inpatient visits

### Clinical Activity

* Number of lab procedures
* Number of medications
* Number of diagnoses
* Diabetes medication indicators

### Operational Context

* Admission type
* Discharge disposition
* Payer type
* Medical specialty

### Outcome Variable

* Hospital readmission status

---

# Machine Learning Model

A **Logistic Regression model** was implemented to estimate the probability that a patient will experience a prolonged hospital stay.

### Target Variable

```
Prolonged Stay = 1 if Length of Stay ≥ 8 days
Prolonged Stay = 0 otherwise
```

### Model Features

* number of lab procedures
* number of medications
* number of diagnoses
* prior outpatient visits
* prior emergency visits
* prior inpatient visits

### Model Output

The model generates:

* **Prolonged stay probability score**
* **Risk segmentation**

Risk segments:

* Low Risk
* Moderate Risk
* High Risk

These predictions are integrated into the dashboard to support **operational decision-making and care management prioritization**.

---

# Dashboard Components

The Qlik dashboard provides operational and predictive insights across multiple categories.

### Executive KPIs

* Average Length of Stay
* 30-Day Readmission Rate
* Average Medications per Patient
* Average Lab Procedures

### Hospital Utilization Analytics

* Readmission Distribution
* Admission Type Distribution

### Predictive Risk Analytics

* Predicted Prolonged Stay Risk Segmentation
* Average Length of Stay by Predicted Risk Level

### Patient Demographics

* Length of Stay by Age Group
* Length of Stay by Race

### Clinical Complexity Drivers

* Medication Burden vs Length of Stay
* Emergency Visits vs Length of Stay

Interactive filters allow segmentation by:

* Age group
* Race
* Admission type
* Payer type
* Medical specialty
* Risk segment

---

# Key Insights

### Prolonged Stay Risk Segmentation

The predictive model segments patients into **low, moderate, and high-risk groups for prolonged hospitalization**. High-risk patients demonstrate significantly longer average hospital stays compared to lower risk cohorts, highlighting opportunities for early intervention and discharge planning.

---

### Clinical Complexity Drives Hospital Utilization

Encounters involving **higher medication counts and greater diagnostic complexity** are associated with longer hospital stays. This pattern suggests that clinical complexity is a primary driver of inpatient resource utilization.

---

### Emergency Utilization and Length of Stay

Patients with **higher levels of prior emergency department utilization** demonstrate longer average hospital stays. Frequent emergency care usage may indicate underlying health instability or gaps in outpatient care management.

---

### Age-Related Differences in Hospital Stay Duration

Average length of stay increases across older patient groups, with the **highest LOS observed among patients aged 70 and above**. This trend likely reflects increased comorbidity burden and greater care complexity among older populations.

---

### Readmission Patterns

Approximately **11% of encounters result in readmission within 30 days**, highlighting the importance of effective discharge planning, follow-up care, and care coordination to reduce avoidable readmissions.

---

### Admission Type and Hospital Utilization

Emergency admissions represent a substantial portion of encounters and tend to demonstrate higher utilization patterns than scheduled admissions, reflecting the operational impact of unscheduled care demand.

---

# Technologies Used

* Python
* SQL
* BigQuery
* Qlik Sense
* Scikit-Learn
* Pandas

---

# Project Structure

```
hospital-length-of-stay-analytics

data/
diabetic_data.csv

notebooks/
prolongedstaymodel.ipynb
ProjectSQLTransformations.ipynb
ProjectDataCleaning.ipynb

dashboard/
dashboard_overview.png

architecture/
pipeline_architecture.pdf
```

---

# Future Improvements

Potential extensions of this project include:

* Gradient boosting or random forest models for improved predictive performance
* Diagnosis-level clinical feature engineering
* Specialty-level hospital utilization analysis
* Cohort analysis by payer type or demographic segment
* Readmission prediction modeling

---

# Author

**Anurag Koripalli**
Business Analytics & Information Management
Purdue University

This project demonstrates an end-to-end healthcare analytics workflow combining **cloud data engineering, predictive modeling, and business intelligence visualization** to support hospital operational decision-making.
