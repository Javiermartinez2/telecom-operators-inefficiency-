# Telecom Operators Inefficiency Analysis

## Project Overview

Telecom operators handle large volumes of incoming calls every day. However, operational inefficiencies such as long waiting times or missed calls are often difficult to detect without a structured, data-driven analysis.

This project analyzes **incoming call data** to identify **operational inefficiencies at the operator level**, using exploratory data analysis (EDA), well-defined performance metrics, and statistical hypothesis testing. The goal is to support **data-driven operational decisions** that improve customer experience and resource allocation.

> **Note:** The detailed analysis notebook is written in Spanish.  
> This README summarizes the project context, methodology, and key insights.

---

## Objectives

- Analyze incoming call data to understand operational performance.
- Identify operators with consistently inefficient behavior.
- Define objective, statistically robust inefficiency criteria.
- Quantify the operational and business impact of inefficiencies.
- Provide actionable insights for operational improvement.

---

## Data Description

The analysis uses two datasets:

- **telecom_dataset_us.csv**  
  Incoming and outgoing call records, including:
  - Call direction (incoming / outgoing)
  - Operator ID
  - Call duration
  - Total call duration
  - Missed calls
  - Internal vs external calls
  - Timestamps

- **telecom_clients_us.csv**  
  Client-level information, including:
  - User ID
  - Tariff plan
  - Subscription start date

The analysis focuses exclusively on **incoming calls**, as they directly reflect customer experience and service efficiency.

---

## Methodology

The project follows a structured analytical approach:

1. **Data Preparation & Cleaning**
   - Type normalization (dates, booleans).
   - Removal of non-evaluable records (e.g. missing operator ID).
   - Creation of derived metrics (e.g. waiting time).
   - Conservative handling of outliers using percentiles.
   - Minimum volume threshold applied to ensure statistical robustness.

2. **Exploratory Data Analysis (EDA)**
   - Distribution of call volumes and durations.
   - Analysis of waiting time asymmetry and extreme values.
   - Operator-level variability exploration.
   - Identification of potential operational bottlenecks.

3. **Definition of Inefficiency Metrics**
   - Average waiting time.
   - Proportion of missed incoming calls.
   - Proportion of calls with elevated waiting time.
   - Total incoming call volume per operator.

4. **Operator Classification**
   - Objective statistical thresholds (percentiles).
   - Minimum volume constraint to avoid low-sample bias.
   - Identification of consistently inefficient operators.

5. **Statistical Validation**
   - Normality testing (Shapiro–Wilk).
   - Non-parametric hypothesis testing (Mann–Whitney U).
   - Validation that observed differences are statistically significant and not random.

---

## Key Insights

- A **subset of operators** shows consistently higher waiting times and missed-call rates.
- Inefficiency is **not random nor marginal**, but **structural and recurrent**.
- Inefficient operators miss **nearly four times more calls on average** than efficient ones.
- A relatively small group of operators concentrates a significant share of problematic calls.
- Differences between efficient and inefficient operators are **statistically significant**.

---

## Business Impact

These insights can help telecom organizations:

- Improve customer experience by reducing waiting times.
- Detect operational bottlenecks early.
- Optimize workforce allocation and workload distribution.
- Prioritize targeted interventions instead of broad corrective actions.
- Support data-driven operational and managerial decisions.

---

## Recommendations

- **Prioritize intervention** on operators identified as inefficient.
- Implement **targeted training and coaching** focused on peak-demand handling.
- Monitor performance **periodically** (monthly or quarterly).
- Use inefficiency metrics as a **preventive tool**, not only for corrective action.
- Continuously recalibrate thresholds based on operational changes.

---

## 🚀 Final Note

This project demonstrates an end-to-end analytical workflow: from raw data to validated business insights.  
It emphasizes **clarity, statistical rigor, and operational relevance**, making it suitable for real-world decision-making contexts.

