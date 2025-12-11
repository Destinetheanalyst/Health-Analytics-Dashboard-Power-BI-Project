# Health-Analytics-Dashboard-Power-BI-Project
---

## **Table of Contents**
1. [Project Overview](#project-overview)  
2. [Business Objectives](#business-objectives)  
3. [Dashboard Features](#dashboard-features)  
4. [Tools & Technologies](#tools--technologies)   
5. [Key DAX Measures](#key-dax-measures)  
6. [Insights & Analysis](#insights--analysis)  
7. [Dashboard Preview](#dashboard-preview)  
8. [Recommendations](#recommendations)  
9. [Skills Demonstrated](#skills-demonstrated)  
10. [Contact](#contact)

---

## **1. Project Overview**
The **Health Analytics Dashboard** is a comprehensive Power BI solution developed to provide hospital administrators and healthcare stakeholders with real-time visibility into clinical performance, patient demographics, hospital operations, and financial indicators.

This project demonstrates advanced capabilities in **data modeling**, **Power Query ETL**, **DAX**, and **executive dashboard development**, aligned with the best practices expected of senior analytics roles.
The dashboard is built for performance, analytical accuracy, and ease of use for decision-makers.

---
<img width="841" height="441" alt="health done" src="https://github.com/user-attachments/assets/6d5e574d-e50d-4397-8c8e-4e50f01be444" />

---

## **2. Business Objectives**
The dashboard was developed to meet the following core objectives:

- Provide a clear breakdown of **patient demographics** and health service utilization.  
- Monitor **hospital operations** to support operational efficiency and capacity planning.  
- Track **clinical performance indicators**, including diagnosis trends and readmission metrics.  
- Offer healthcare management a **unified, high-level view** of institutional performance.  
- Enable robust **data-driven decision-making** in clinical and administrative functions.

---

## **3. Dashboard Features**

### **A. Patient Demographics**
- Age-group analysis  
- Gender statistics  
- Patient type distribution (inpatient vs outpatient)

### **B. Hospital Operations**
- Monthly admissions and discharge trends  
- Appointment attendance vs no-shows  
- Readmission analysis  
- Average length of stay

### **C. Clinical Performance**
- Diagnosis categories  
- Treatment categories  
- Department-level performance  
- Doctor activity and patient load

### **D. Financial Performance (Optional)**
- Billing and revenue overview  
- Department-level revenue  
- Average billing per patient  
- Outstanding balances

---

## **4. Tools & Technologies**
| Technology | Purpose |
|-----------|---------|
| **Power BI Desktop** | Data modeling, dashboard creation |
| **Power Query** | ETL and data transformation |
| **DAX** | Measures, KPIs, and analytics logic |
| **Excel / CSV** | Dataset management |
| **GitHub** | Version control and documentation |

---

## **5. Key DAX Measures**

``` DAX
Total Patients =
COUNTROWS(Patients)

Total Admissions =
COUNTROWS(Fact_Admissions)

Readmission Rate =
DIVIDE(
    CALCULATE(
        COUNTROWS(Fact_Admissions),
        Fact_Admissions[IsReadmission] = "Yes"
    ),
    [Total Admissions]
)

Average Length of Stay =
AVERAGE(Fact_Admissions[Length_of_Stay])
```

## **6. Insights & Analysis**

---

### **1. Overall Patient Waitlist Growth**

The dashboard reveals a **significant year-over-year increase** in the total number of patients on the waitlist:

- **Last Month Waitlist:** 709K  
- **Previous Year Last Month:** 640K  

This represents a **10.8% annual increase**, indicating sustained pressure on health system capacity and a growing mismatch between service demand and available resources.

---

### **2. Specialty-Level Wait Time Variability**

Patient experience varies widely across clinical specialties, with several paediatric services emerging as high-risk bottlenecks.

#### Specialties with the Longest Average Wait Times:
- **Paediatric Dermatology:** 167.89 days  
- **Paediatric ENT:** 147.55 days  
- **Paediatric Orthopaedic:** 114.50 days  
- **Accident & Emergency:** 111.19 days  

These values indicate **critical capacity constraints** within paediatric care pathways and emergency intake. The pattern suggests rising demand, inadequate specialist availability, or workflow inefficiencies.

---

### **3. Age-Profile Influence on Waiting Times**

Analysis of the **Patient Wait List (Average)** by age bands indicates:

- The largest waitlist volumes fall within the **0–15** and **16–64** age groups.
- Patients aged **65+**, although fewer in number, experience **longer wait durations** across several time bands.

This demonstrates potential **access inequities affecting older patients**, which may increase downstream clinical risk such as emergency admissions or complications due to delayed treatment.

---

### **4. Case Type Distribution: Inpatient Pressure Dominates**

The case-type donut visual shows the share of Average/Median wait time across:

- **Inpatient cases carry the highest burden**, comprising *approximately 54.38%* of the total waitlist pressure.
- Outpatient and day-case volumes are comparatively smaller.

This indicates that **inpatient throughput constraints**—often tied to bed availability and discharge processes—represent the most significant contributor to overall delays.

---

### **5. Multi-Year Trend Analysis (2018–2021)**

#### Inpatient Trends
- Inpatient volume declined from **57K (2018)** to about **40K**, but then **spiked to 51K and 62K by 2021**.
- This reflects a temporary improvement followed by significant deterioration, likely linked to post-pandemic demand spikes and deferred elective care.

#### Day Case Trends
- Day-case volumes dropped sharply from **23K** and recovered only marginally to **21K** by 2021.
- This slow rebound suggests persistent resource constraints or priority shifts.

#### Outpatient Trends
- Outpatient backlog shows the steepest climb: **516K → 560K → 513K → 629K** (2018–2021).
- The 2021 increase to **629K** signals a **major access issue in first-contact services**, with long-term implications for diagnosis delays and disease progression.

---

### **6. Average vs. Median Wait Time Patterns**

The comparison between average and median wait times reveals a **positively skewed distribution**, where:

- **Average wait times exceed median wait times**, indicating the presence of long-wait outliers.
- These long-wait patients disproportionately inflate system-wide averages and require targeted backlog-clearing initiatives.

---
The analysis identifies a systemic pattern of operational friction, fragmented care coordination, and substantial financial leakage. These issues collectively demonstrate the consequences of a predominantly *reactive* healthcare delivery model, especially for patients with complex conditions.

#### Clinical–Financial Risk Burden  
- **High 30-day readmission rates** are heavily concentrated among patients with chronic and comorbid conditions—particularly **mental health disorders, diabetes, and cardiovascular diseases**.  
- These patient groups also exhibit **longer initial hospital stays**, amplifying both cost and clinical risk exposure.  
- A major gap in current workflows is the **absence of Social Determinants of Health (SDOH)** in risk stratification.  
    - As a result, many high-risk patients are **not flagged early**.  
    - Transitional care plans are triggered reactively instead of proactively.  
- This oversight leads to repeat admissions, avoidable complications, and measurable financial strain.

#### Operational Inefficiencies and Systemic Waste  
- **Average Length of Stay (ALOS)** frequently exceeds the **Geometric Mean Length of Stay (GMLOS)** across multiple DRG groups.  
    - This variance translates directly into **avoidable inpatient cost overruns**.  
- Process bottlenecks such as **high Time to Provider (T2P)** and delays in interdepartmental workflows reduce throughput and constrain capacity.  
- These operational inefficiencies also diminish patient satisfaction and staff productivity, reinforcing a cycle of reactive care.

#### Recoverable Revenue Leakage  
- The organization experiences a **high Claims Denial Rate**, driven primarily by preventable **front-end administrative errors**, including:  
    - Incorrect or incomplete registration data  
    - Insurance eligibility issues  
    - Missing or incorrect prior authorizations  
- These denials represent **immediate revenue loss**.  
- Manual review processes cannot keep pace with the volume or complexity of claims, resulting in recurring leakage rather than systemic correction.
  
 ---
<img width="844" height="445" alt="health done 1" src="https://github.com/user-attachments/assets/524d8535-9a40-481a-831a-fdf3e9c51081" />


## **8. Recommendations**

### **1. Strengthen Capacity & Scheduling Optimization**  
- Prioritize paediatric services and A&E, where wait times exceed safe thresholds.  
- Implement dynamic scheduling and automated load balancing.

### **2. Increase Outpatient Throughput**  
- Expand clinician sessions, extend clinic hours, or adopt hybrid consultation models.  
- Improving outpatient flow prevents future inpatient surges.

### **3. Improve Inpatient Bed Management**  
- Deploy real-time bed tracking and discharge planning tools.  
- Reduce avoidable delays to improve inpatient turnaround.

### **4. Target Long-Wait Outliers**  
- Establish a structured backlog-clearing program.  
- Use predictive analytics to identify at-risk patient groups and minimize delays.
  
### **5. Mandate SDOH-Adjusted Care Coordination**  
To reduce readmissions and optimize patient flow:

- Implement a **predictive risk scoring model** that integrates:  
  - Clinical history  
  - Comorbidity severity  
  - Utilization patterns  
  - **External SDOH datasets** (income, housing stability, transportation access, neighborhood risk indicators)  
- Use these enhanced risk scores to identify high-risk patients **at the point of admission**, not after discharge.  
- Deploy dedicated **Multidisciplinary Discharge Planning Teams** to these high-risk cases.  
- Standardize an optimized discharge workflow targeting alignment of ALOS with GMLOS benchmarks.  
- Establish a structured **4-to-10-day post-discharge follow-up program**, tailored to the risk factors flagged by the predictive model.

This approach transitions the organization from reactive to **anticipatory care management**, minimizing complications and improving patient outcomes.

### **6. Invest in AI-Driven Revenue Cycle Automation**  

To reclaim lost revenue and stabilize cash flow:

- Implement AI solutions for:  
  - Real-time claims scrubbing  
  - Automated eligibility and authorization checks  
  - Intelligent routing of exception cases  
- Automate the majority of **front-end validation**, which currently drives most denial root causes.  
- Improve first-pass clean claim rates, accelerating **Days in A/R reduction** and strengthening financial predictability.  
- Enable staff to shift from repetitive manual tasks toward **exception management and strategic financial oversight**.

This investment produces **rapid, measurable ROI**, directly addressing the organization’s largest source of preventable financial leakage.

## 9. Skills Demonstrated

- **Advanced Power BI Dashboard Development**  
  Designed an interactive, multi-page analytical dashboard with dynamic slicers, KPI cards, and drill-through insights tailored for healthcare operations.

- **DAX and Data Modeling Expertise**  
  Developed complex DAX measures, calculated tables, and custom time-intelligence logic to support accurate patient waitlist analytics and historical comparisons.

- **Power Query Transformation Workflows**  
  Cleaned, reshaped, merged, and standardized diverse datasets using Power Query M-language to ensure data integrity and optimal refresh performance.

- **Fact/Dimension Schema Design**  
  Implemented a robust star-schema model to separate facts from dimensions, enabling efficient aggregation, slicing, and filtering across multiple performance metrics.

- **Performance Optimization**  
  Applied best practices, including column reduction, measure optimization, and relationship tuning to enhance dashboard responsiveness and minimize resource consumption.

- **Data Analysis, Healthcare KPIs, and Reporting**  
  Translated raw health service data into interpretable metrics such as ALOS, GMLOS, waitlist trends, specialty-level KPIs, age-band insights, and multi-year backlog patterns.

- **Storytelling for Executive Decision-Making**  
  Synthesized complex operational data into clear, actionable insights for senior leaders, ensuring the dashboard supports strategic planning, capacity management, and policy decisions.

---

## 10. Contact

**Name:** Dike Nnaemeka Destine  
**Role:** Data Analyst | BI Developer | Instructor  

**GitHub:**  
[https://github.com/Destinetheanalyst](https://github.com/Destinetheanalyst)

**LinkedIn:**  
[https://www.linkedin.com/in/nnaemeka-destine-dike-9a27b531a](https://www.linkedin.com/in/nnaemeka-destine-dike-9a27b531a)
