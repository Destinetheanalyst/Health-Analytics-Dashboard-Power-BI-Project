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

This project reflects advanced capabilities in **data modeling**, **Power Query ETL**, **DAX**, and **executive dashboard development**, aligned with best practices expected from senior analytics roles.

The dashboard is built for performance, analytical accuracy, and ease of use for decision-makers.

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


