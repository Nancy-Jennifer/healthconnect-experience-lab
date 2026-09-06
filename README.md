# **HealthConnect Experience Lab**

## *Improving Patient Appointment Attendance and Healthcare Support Using Data and AI*

### **Data Analytics Track | AnalystLab Africa Internship Programme**

**Author:** Nancy Lee YIMBERE ALAPINI  
**Professional Focus:** *Performance & Decision Intelligence Analyst*  
**Project Status:** **Week 5 — Analytics Development & Initial Implementation Completed**

> *A progressive analytics project translating appointment data into evidence-based decision support for patient attendance.*

---
## **1. Project Overview**

The HealthConnect Experience Lab is a multidisciplinary project developed as part of the AnalystLab Africa Internship Programme.

HealthConnect Clinic faces challenges related to missed appointments, cancellations, and patient support needs.

Core business question: How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?

For the Data Analytics Track, the objective is to understand attendance patterns, evaluate analytical hypotheses, develop decision-relevant KPIs, and translate validated evidence into actionable priorities.

## **2. Week 5 Deliverables**

The Week 5 deliverables are stored in the repository's notebooks, dashboards, and reports folders.

Deliverable

Purpose

Week 5 Analytics Notebook (.ipynb)

Data preparation, EDA, hypothesis evaluation and KPI calculations

Week 5 Power BI Dashboard (.pbix)

Decision-support dashboard: MONITOR → DIAGNOSE → PRIORITIZE

Business Insights & Recommendations (.pdf)

Validated findings, business implications and recommendations

Week 5 Project Summary (.pdf)

Concise Week 5 implementation summary

Week 4 Foundation Deliverables

Deliverable

Purpose

Initial Analysis Document (.pdf)

Week 4 analytical foundation

Technical Data Inspection Notebook (.ipynb)

Reproducible technical inspection

Technical Data Inspection Notebook (.pdf)

Readable technical notebook export

Week 4 Project Summary (.pdf)

Concise analytical foundation summary

## **3. Project Continuity**

The HealthConnect Experience Lab is a progressive multi-week project.

Week 4 — UNDERSTAND → REVIEW → DEFINE → PLAN
Week 5 — PREPARE → ANALYSE → VALIDATE → MONITOR → DIAGNOSE → PRIORITIZE
Week 6 — REFINE → INTEGRATE

Week 4 established the analytical foundation. Week 5 moved the project into practical analysis, KPI development, evidence validation, dashboard implementation and decision support.

WEEK 4 — ANALYTICAL FOUNDATION

## **4. Week 4 Objective**

Week 4 focused on understanding and structuring the problem before executing the analysis.

The foundation included:

review of the dataset and Data Dictionary;

initial data-quality assessment;

definition of the appointment record as the unit of analysis;

six Business Questions;

twelve analytical hypotheses;

three potential KPIs;

an initial analysis approach;

assumptions, limitations, risks and dependencies.

Week 4 principle: UNDERSTAND → REVIEW → DEFINE → PLAN

WEEK 5 — ANALYSIS & INITIAL IMPLEMENTATION

## **5. Week 5 Objective**

Week 5 moved from analytical planning to practical implementation:

data preparation and quality validation;

EDA structured by Business Question;

hypothesis evaluation;

KPI calculation and interpretation;

Power BI dashboard development;

evidence hierarchy and prioritisation;

business insights and recommendations;

documentation of limitations and interpretation guardrails.

The analysis remained question-driven rather than chart-driven.

## **6. Data Preparation & Quality Validation**

Check

Result

Analytical Treatment

Dataset structure

5,000 rows × 18 columns

Expected structure retained

appointment_id

5,000 unique

Appointment-level unit of analysis confirmed

Exact duplicate rows

0

No duplicate removal required

Missing distance_to_clinic_km

90 (1.8%)

No automatic imputation

Missing waiting_time_minutes

60 (1.2%)

No automatic imputation

reminder_channel = None

1,366 records

Structural N/A when no reminder was sent

Repeated patient-level inconsistencies

Present

No longitudinal patient reconstruction

Data-quality guardrail: the appointment record remains the unit of analysis.

## **7. KPI Framework**

KPI

Definition

Week 5 Result

Business Question

No-Show Rate (%)

No-Shows / (Attended + No-Show)

51.15%

BQ1

Reminder Coverage Rate (%)

Appointments with reminder / All appointments

72.68%

BQ3

No-Show Rate by Reminder Status

Comparison across reminder status

54.63% No Reminder / 49.86% Reminder Sent

BQ3

Supporting metric: No-Reminder Gap = +4.78 percentage points

Reminder exposure is interpreted as an observed association, not as evidence of causal effectiveness.

## **8. Key Analytical Findings**

**8.1 Overall Appointment Outcome**

Outcome Metric

Result

Total Appointments

5,000

No-Show

2,423

Attended

2,314

Cancelled

263

Non-Cancelled Analytical Population

4,737

Overall No-Show Rate

51.15%

**8.2 Booking Lead Time — Clearest Observed Differentiation**

Booking Lead Time

No-Show Rate

0–7 days

29.47%

8–14 days

35.19%

15–30 days

45.53%

31–45 days

57.03%

46–60 days

71.36%

Spearman ρ = 0.2873, p < 0.001

Interpretation: Booking lead time shows the clearest observed differentiation in No-Show Rates among the factors examined.

**8.3 Recorded Previous No-Shows — Supporting History Signal**

Recorded Previous No-Shows

No-Show Rate

0

46.30%

1

55.87%

2

62.05%

3

69.74%

Observed 0-to-3 gap: +23.43 percentage points
Spearman ρ = 0.1214, p < 0.001

Interpretation: Recorded previous no-shows provide a useful supporting prioritisation signal, but should not be treated as a standalone predictor.

**8.4 Reminder Exposure — Weak Observed Differentiation**

Reminder Metric

Result

Reminder Coverage Rate

72.68%

No Reminder — No-Show Rate

54.63%

Reminder Sent — No-Show Rate

49.86%

No-Reminder Gap

+4.78 pp

Cramér's V

≈ 0.042

The difference is statistically detectable, but the association is very weak.

Coverage ≠ Effectiveness. Association ≠ Causation.

## **9. Evidence Hierarchy**

Evidence Level

Factors

Primary Signals

Booking Lead Time; Recorded Previous No-Shows

Secondary Signals

Reminder Exposure; Distance to Clinic

Contextual Signals

Appointment Type; Previous Appointments; Reminder Channel

No Standalone Prioritisation

Appointment Day; Appointment Time; Waiting Time; Age Group; Gender

The hierarchy considers descriptive evidence, statistical significance, effect size, stability, data quality and decision relevance rather than relying on p-values alone.

POWER BI DECISION-SUPPORT DASHBOARD

## **10. MONITOR → DIAGNOSE → PRIORITIZE**

The dashboard is designed as a decision-support journey rather than a collection of unrelated charts.

**01 | MONITOR**

Decision question: What is the current appointment-attendance situation?



Decision signal: No-show exposure is high overall, while reminder status provides only limited differentiation. Further diagnosis should focus on factors showing stronger variation in No-Show Rates.

**02 | DIAGNOSE**

Decision question: Which factors meaningfully differentiate No-Show Rates?



Diagnostic signal: Booking lead time shows the clearest differentiation, while recorded previous no-shows provide a useful supporting signal.

**03 | PRIORITIZE**

Decision question: Where should HealthConnect focus analytical and operational attention first?



Priority

Decision Direction

Monitoring

1 — Long Booking Lead Times

Assess targeted pre-appointment engagement for appointments booked 31–60 days in advance

No-Show Rate by Booking Lead Band

2 — Recorded Previous No-Shows

Use recorded history as a supporting prioritisation signal

No-Show Rate by Recorded Previous No-Shows

Investigate — Reminder Strategy

Assess reminder timing, targeting and channel strategy before intervention changes

Reminder-related attendance metrics

Do Not Prioritise in Isolation

Appointment Day, Appointment Time, Waiting Time, Age Group and Gender

Continue monitoring only if analytically relevant

## **11. Business Insights & Recommendations**

**Recommendation 1 — Prioritise Long Booking Lead Times**

Focus first on appointments booked 31–60 days in advance, with particular attention to the 46–60 day group.

**Recommendation 2 — Use Previous No-Shows as a Supporting Signal**

Consider additional follow-up where multiple recorded previous no-shows occur alongside higher-risk scheduling contexts.

**Recommendation 3 — Investigate Reminder Strategy Before Modifying It**

Assess reminder timing, targeting and channel strategy before changing reminder interventions.

**Recommendation 4 — Avoid Targeting Weakly Differentiating Factors**

Current evidence does not support standalone prioritisation based solely on appointment day, appointment time, waiting time, age group or gender.

## **12. Interpretation Guardrails**

Correlation ≠ Causality

Benchmark ≠ Target

Statistical significance alone does not establish decision relevance.

Weak associations are not promoted to primary drivers.

Sparse categories are not used to define intervention thresholds.

Patient-level histories are not reconstructed from inconsistent repeated patient_id records.

Recommendations remain proportionate to the evidence available in Week 5.

## **13. Cross-Track Collaboration Status**

Cross-track collaboration was not completed within the Week 5 submission window.

Priority was given to completing, validating and documenting the Data Analytics track deliverables rather than claiming an exchange that had not occurred.

This dependency remains open for Week 6.

## **14. Week 6 Focus**

The next phase should focus on:

testing whether combinations of Booking Lead Time + Recorded Previous No-Shows improve prioritisation;

refining intervention hypotheses without converting associations into causal claims;

investigating reminder timing, targeting and channel strategy;

initiating meaningful cross-track collaboration where relevant;

refining and testing the initial analytical outputs;

maintaining KPI traceability and cross-deliverable consistency.

## **15. Analytical Method**

Business Problem → Business Questions → Hypotheses → Data → Analysis → Findings → Insights → Business Implications → Recommendations → Decision Support

The Week 5 dashboard operationalises this logic through:

MONITOR → DIAGNOSE → PRIORITIZE

The objective is not to maximise the number of analytical outputs, but to establish which results are sufficiently supported to deserve a place in decision-making.

**Project Status**

Week 4 — Analytical Foundation: Completed

Week 5 — Analysis, KPI Development & Initial Implementation: Completed

Week 6 — Refinement & Integration: Next phase
