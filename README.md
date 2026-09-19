# HealthConnect Experience Lab

## Improving Patient Appointment Attendance and Healthcare Support Using Data and AI

**Track:** Data Analytics  
**Analyst:** Nancy Lee YIMBERE ALAPINI  
**Professional Focus:** Performance & Decision Intelligence  
**Programme:** AnalystLab Africa Internship Programme  
**Project Status:** Week 7 — Testing, Refinement & End-to-End Validation Completed

> Current analytical focus: testing, refining and validating the HealthConnect decision-support solution before Week 8 final integration.

---

## Project Overview

HealthConnect Experience Lab is a multi-week analytics project focused on understanding patient appointment attendance patterns and supporting better operational decision-making around patient attendance.

The project progressively moves from business understanding and data-quality assessment to exploratory analysis, KPI development, advanced validation, cross-track integration, dashboard refinement and end-to-end testing.

The central business question is:

> How can HealthConnect use appointment data to better understand attendance patterns, identify meaningful no-show signals, prioritise attendance-support actions, and improve decision-making without overstating what the available data can prove?

The analytical unit remains the **appointment record**.

The project does not reconstruct reliable longitudinal patient histories because patient-level consistency checks identified limitations in recorded demographic and historical variables.

---

# Quick Navigation — Week 7 Deliverables

### Main Analytics Testing & Refinement Report
[View Week 7 Analytics Testing & Refinement Report](reports/WK7_HealthConnect_Analytics_Testing_Refinement_Report_Nancy_Lee_YIMBERE_ALAPINI.pdf)

### Week 7 Project Summary
[View Week 7 Project Summary](reports/WK7_HealthConnect_Project_Summary_Nancy_Lee_YIMBERE_ALAPINI.pdf)

### Testing & Validation Evidence Pack
[Download Week 7 Testing & Validation Evidence Pack](analysis/WK7_HealthConnect_Testing_Validation_Evidence_Pack_Nancy_Lee_YIMBERE_ALAPINI.xlsx)

### Power BI Dashboard
[Download Week 7 Power BI Dashboard](dashboards/WK7_HealthConnect_Analytics_Dashboard_Nancy_Lee_YIMBERE_ALAPINI.pbix)

### HC-POD Cross-Track Evidence
[View Week 7 HC-POD Cross-Track Evidence](reports/WK7_HealthConnect_HC-POD_Cross-Track_Evidence_Nancy_Lee_YIMBERE_ALAPINI.pdf)

### Data Analytics × Data Science Collaborative Evidence
[View DA × DS Cross-Track Testing & Validation Evidence](notebooks/WK7_HealthConnect_DA_DS_Cross-Track_Testing_Validation_Evidence.pdf)

---

# Project Continuity

The HealthConnect project follows a progressive analytical workflow.

### Week 4 — Analytical Foundation

**UNDERSTAND → REVIEW → DEFINE → PLAN**

Business understanding, dataset review, data-quality assessment, analytical questions, hypotheses and initial KPI framework.

### Week 5 — Analysis & Initial Implementation

**PREPARE → ANALYSE → VALIDATE → MONITOR → DIAGNOSE → PRIORITIZE**

Data preparation, exploratory data analysis, KPI development, statistical validation, Power BI dashboard development and initial decision-support recommendations.

### Week 6 — Advanced Analytics & Decision Support

**SELECT → DEEPEN → VALIDATE → INTEGRATE → DECIDE → PREPARE TO TEST**

Week 6 strengthened the analytical evidence hierarchy through robustness analysis, combined-signal analysis, multivariable modelling, Data Analytics × Data Science integration, measurable recommendation design and decision-support refinement.

### Week 7 — Testing, Refinement & End-to-End Validation

**REVIEW → TEST → COMPARE → VALIDATE → REFINE → RE-TEST → DOCUMENT**

Week 7 challenged the existing solution rather than introducing a new analysis.

The focus was to determine whether the Week 6 outputs were:

- correctly calculated;
- analytically robust;
- consistently represented in Power BI;
- safe to interpret under dashboard interactions;
- aligned with evidence strength;
- useful for operational decision support;
- consistent with Data Science findings;
- ready for Week 8 integration.

---

# WEEK 4 — ANALYTICAL FOUNDATION

## Week 4 Objective

Week 4 established the analytical foundation of the HealthConnect project.

The work focused on:

- understanding the business problem;
- reviewing the appointment dataset and data dictionary;
- assessing data quality;
- identifying analytical limitations;
- defining relevant business questions;
- formulating analytical hypotheses;
- identifying potential KPIs;
- defining an initial analysis approach.

---

## Dataset Overview

The HealthConnect appointment dataset contains:

- **5,000 appointment records**
- **18 variables**
- **5,000 unique appointment IDs**
- **1,696 distinct patient IDs**

The appointment period runs from:

**1 January 2025 → 30 June 2026**

The dataset contains information related to:

- appointment outcomes;
- appointment type;
- booking and appointment dates;
- booking lead time;
- appointment day and time;
- reminder status and channel;
- recorded previous appointments;
- recorded previous no-shows;
- distance to clinic;
- estimated waiting time;
- age, age group and gender.

### Patient-Level Limitation

Repeated `patient_id` values showed inconsistencies across some demographic and historical fields.

Therefore:

> **The appointment record remains the analytical unit, and reliable longitudinal patient histories are not reconstructed from the dataset.**

---

# WEEK 5 — ANALYSIS & INITIAL IMPLEMENTATION

## Week 5 Objective

Week 5 transformed the analytical foundation into an initial decision-support system through:

- data preparation;
- exploratory data analysis;
- KPI development;
- statistical validation;
- Power BI dashboard development;
- evidence-based findings;
- initial recommendations.

---

## Week 5 Outcome Baseline

| Appointment Outcome | Count |
|---|---:|
| No-Show | 2,423 |
| Attended | 2,314 |
| Cancelled | 263 |
| **Total** | **5,000** |

For attendance analysis, cancelled appointments are excluded because they do not reach the point at which attendance versus no-show is observable.

### Attendance-Observable Population

**Attended + No-Show = 4,737 appointments**

---

## KPI Framework

### 1. No-Show Rate — Primary Outcome KPI

**Formula**

`No-Shows / (No-Shows + Attended)`

**Value: 51.15%**

This is a descriptive performance reference, not an external benchmark or target.

### 2. Reminder Coverage Rate — Secondary Process KPI

**Formula**

`Appointments with Reminder Sent / Total Appointments`

**Value: 72.68%**

This measures reminder-process execution, not reminder effectiveness.

### Diagnostic Comparative Metric

No-Show Rate by Reminder Status:

- No Reminder: **54.63%**
- Reminder Sent: **49.86%**
- Observed Gap: **4.78 percentage points**

This is retained as a diagnostic metric, not as a standalone outcome KPI.

---

# WEEK 6 — ADVANCED ANALYTICS & DECISION SUPPORT

## Week 6 Objective

Week 6 moved beyond initial exploratory findings.

The objective was to determine whether the most important Week 5 findings remained meaningful after deeper analytical validation and whether they could support defensible operational decisions.

The Week 6 workflow was:

**WEEK 5 EVIDENCE → SELECT → DEEPEN → VALIDATE → PRIORITIZE → HANDOFF → INTEGRATE → DECIDE → ACT → MONITOR → PREPARE TO TEST**

---

## Week 6 KPI Revalidation

| Measure | Week 6 Classification | Value |
|---|---|---:|
| No-Show Rate | Primary Outcome KPI | **51.15%** |
| Reminder Coverage Rate | Secondary Process KPI | **72.68%** |
| No-Show Rate by Reminder Status | Diagnostic Comparative Metric | **54.63% vs 49.86%** |
| No-Reminder Gap | Supporting Diagnostic Metric | **+4.78 pp** |

No additional KPI was introduced simply because a variable showed statistical differentiation.

> A metric becomes a management KPI only when it is connected to a decision, action or process that needs to be monitored.

---

## Week 6 Analytical Evidence Hierarchy

### PRIMARY SIGNAL — Booking Lead Time

Booking Lead Time remained the strongest observed differentiation in No-Show Rates.

| Booking Lead Time | No-Show Rate |
|---|---:|
| 0–7 days | 29.47% |
| 8–14 days | 35.19% |
| 15–30 days | 45.53% |
| 31–45 days | 57.03% |
| 46–60 days | 71.36% |

Simplified comparison:

| Booking Lead Time | No-Show Rate |
|---|---:|
| 0–30 days | **39.13%** |
| 31–60 days | **63.95%** |

**Observed Gap: +24.82 percentage points**

The relationship is observational and does not establish that longer booking lead time causes no-shows.

---

### SUPPORTING / COMPLEMENTARY SIGNAL — Recorded Previous No-Shows

| Recorded Previous No-Shows | No-Show Rate |
|---|---:|
| 0 | 46.30% |
| 1 | 55.87% |
| 2 | 62.05% |
| 3+ | 70.33% |

Robust comparison:

- Previous NS = 0 → **46.30%**
- Previous NS ≥ 1 → **57.83%**
- Observed Gap → **+11.53 pp**

Recorded Previous No-Shows provides complementary differentiation but remains subject to patient-history data-quality limitations.

---

### Combined-Signal Analysis

| Booking Lead Time | Previous NS = 0 | Previous NS ≥ 1 | Total |
|---|---:|---:|---:|
| 0–30 days | **34.52%** | **45.62%** | **39.13%** |
| 31–60 days | **59.07%** | **70.52%** | **63.95%** |
| **Total** | **46.30%** | **57.83%** | **51.15%** |

The two signals provide complementary differentiation.

They support group-level prioritisation for testing.

They do **not** constitute a deterministic individual risk score.

---

# WEEK 7 — TESTING, REFINEMENT & END-TO-END VALIDATION

## Week 7 Objective

Week 7 did not replace the Week 6 analysis.

It tested it.

The objective was to verify that:

- important findings were accurate;
- KPI definitions and calculations were correct;
- Power BI values reconciled with the analytical source;
- dashboard interactions did not create misleading interpretations;
- findings remained robust under additional testing;
- recommendations remained proportional to evidence strength;
- Analytics-informed modelling decisions could withstand Data Science testing;
- the overall solution was ready for Week 8 integration.

### Week 7 Validation Chain

> **TEST → FINDING → ACTION → RETEST → VALIDATED IMPROVEMENT**

---

# Week 7 Testing Scope

Fourteen Analytics tests were completed.

| Test | Component | Final Outcome |
|---|---|---|
| T01 | Overall No-Show Rate | **PASS** |
| T02 | Reminder Coverage | **PASS** |
| T03 | Booking Lead Time | **PASS** |
| T04 | Recorded Previous No-Shows | **PASS** |
| T05 | Combined Prioritisation Matrix | **PASS** |
| T06 | Dashboard Values & Measures | **PASS** |
| T07 | Filter Behaviour | **REFINED + PASS** |
| T08 | Dashboard Interpretation | **REFINED + PASS** |
| T09 | Reminder Status | **PASS** |
| T10 | Distance to Clinic | **PASS** |
| T11 | Appointment Type × Lead Time | **PASS** |
| T12 | Recommendations | **REFINED + PASS** |
| T13 | Control Variables | **PASS** |
| T14 | Reminder Channel | **PASS** |

Detailed testing evidence is available here:

[Download Week 7 Testing & Validation Evidence Pack](analysis/WK7_HealthConnect_Testing_Validation_Evidence_Pack_Nancy_Lee_YIMBERE_ALAPINI.xlsx)

---

# Week 7 KPI Validation

Independent recalculation confirmed the core KPI framework.

| KPI | Validated Population / Formula | Result |
|---|---|---:|
| Total Appointments | Full dataset | **5,000** |
| Attendance-Observable Appointments | Attended + No-Show | **4,737** |
| Overall No-Show Rate | 2,423 / 4,737 | **51.15%** |
| Reminder Coverage | 3,634 / 5,000 | **72.68%** |

### Validation Outcome

> **Core KPI definitions, denominators and dashboard values were independently revalidated and reconciled.**

No KPI inconsistency remained after Week 7 testing.

---

# Week 7 Analytical Validation

## 1. Booking Lead Time — PRIMARY

Week 7 confirmed Booking Lead Time as the strongest standalone analytical differentiation of No-Show behaviour.

- 0–30 days: **39.13%**
- 31–60 days: **63.95%**
- Observed Gap: **+24.82 pp**
- Spearman ρ ≈ **0.287**
- Odds Ratio per additional 10 booking-lead days ≈ **1.42**

### Final Classification

**PRIMARY**

---

## 2. Recorded Previous No-Shows — SUPPORTING / COMPLEMENTARY

- Previous NS = 0: **46.30%**
- Previous NS ≥ 1: **57.83%**
- Observed Gap: **+11.53 pp**

The signal remains useful for refining group-level prioritisation but is not treated as a verified longitudinal patient-history measure.

### Final Classification

**SUPPORTING / COMPLEMENTARY**

---

## 3. Reminder Status — SECONDARY / CONTEXTUAL

- No Reminder: **54.63%**
- Reminder Sent: **49.86%**
- Observed Gap: **+4.78 pp**
- Phi ≈ **0.042**

The difference is observational and weak in effect magnitude.

It does not demonstrate reminder effectiveness.

### Final Classification

**SECONDARY / CONTEXTUAL**

---

## 4. Distance to Clinic — SECONDARY / CONTEXTUAL

Standalone Analytics testing produced:

**Spearman ρ ≈ 0.055**

The relationship is too weak to justify standalone operational targeting.

### Final Classification

**SECONDARY / CONTEXTUAL**

---

# Robustness Testing — Appointment Type × Booking Lead Time

Week 7 tested whether the Booking Lead Time pattern depended materially on Appointment Type.

| Appointment Type | 0–30 vs 31–60 Day NSR Gap |
|---|---:|
| Diagnostic | **+22.24 pp** |
| Follow-up | **+28.73 pp** |
| General | **+23.51 pp** |
| Specialist | **+23.16 pp** |

The formal interaction test produced:

**p ≈ 0.326**

### Validation Outcome

Booking Lead Time remained robust across Appointment Types.

The evidence did **not** support introducing a separate Follow-up-specific analytical rule.

---

# Final Week 7 Evidence Hierarchy

## PRIMARY SIGNAL

### Booking Lead Time

**Evidence strength:** High  
**Decision relevance:** High

Booking Lead Time remains the strongest and most robust standalone analytical differentiation of No-Show behaviour.

---

## SUPPORTING / COMPLEMENTARY SIGNAL

### Recorded Previous No-Shows

**Evidence strength:** Moderate-to-strong  
**Decision relevance:** Moderate-to-high

Provides additional differentiation beyond Booking Lead Time while remaining subject to patient-history data-quality limitations.

---

## SECONDARY / CONTEXTUAL SIGNALS

### Reminder Status

Limited observed differentiation.

The current observational evidence does not establish reminder effectiveness.

### Distance to Clinic

Weak standalone Analytics association.

Retained for multivariable Data Science modelling after Week 7 cross-track validation.

---

## NO STANDALONE PRIORITISATION

The following variables did not demonstrate sufficient standalone decision value in the current Data Analytics evidence:

- Appointment Type
- Appointment Day
- Appointment Time
- Previous Appointments
- Waiting Time
- Age Group
- Gender
- Reminder Channel

These variables may still provide contextual or multivariable information, but the current Analytics evidence does not justify using them independently for operational prioritisation.

---

# Week 7 Dashboard Testing & Refinement

A genuine dashboard interpretation issue was identified during filter testing.

Interactive subgroup filters could change visual values while some static analytical conclusions continued to represent the validated reference population.

This created a risk that a global analytical conclusion could be interpreted as if it described the currently filtered subgroup.

### Refinement

The final dashboard architecture was clarified as:

**MONITOR → Interactive Operational Exploration**

**DIAGNOSE → Validated Analytical Reference View**

**PRIORITIZE → Validated Decision-Support Reference View**

Static elements vulnerable to filter-context mismatch were removed or revised.

Explicit interaction guidance was added.

The dashboard was then retested.

### Final Outcome

> **REFINED → RETESTED → VALIDATED**

---

# Week 7 Power BI Decision-Support Dashboard

## 01 | MONITOR — Performance Overview

**Purpose:** Monitor overall appointment outcomes and reminder-process coverage while allowing operational exploration.

![HealthConnect Week 7 Monitor Dashboard](assets/week7/WK7_HealthConnect_Dashboard_01_MONITOR_Performance_Overview.png)

### Core Metrics

- No-Show Rate: **51.15%**
- Reminder Coverage Rate: **72.68%**
- Total Appointments: **5,000**
- Attendance-Observable Appointments: **4,737**

### Interaction Rule

> **INTERACTION | Use filters to explore performance across operational contexts.**

---

## 02 | DIAGNOSE — No-Show Differentiation

**Purpose:** Identify which factors meaningfully differentiate observed No-Show Rates.

![HealthConnect Week 7 Diagnose Dashboard](assets/week7/WK7_HealthConnect_Dashboard_02_DIAGNOSE_No-Show_Differentiation.png)

### Diagnostic Conclusion

Booking Lead Time remains the strongest and most robust observed differentiation in No-Show Rates.

Recorded Previous No-Shows provides complementary differentiation.

Other examined factors show weaker or limited standalone decision value.

### Interpretation Rule

> **VALIDATED VIEW | Interpret findings in the reference analytical population; do not apply subgroup filters.**

---

## 03 | PRIORITIZE — Attention Priorities

**Purpose:** Translate validated analytical evidence into actionable attendance-support priorities.

![HealthConnect Week 7 Prioritize Dashboard](assets/week7/WK7_HealthConnect_Dashboard_03_PRIORITIZE_Attention_Priorities.png)

### Priority Framework

#### 1 | PRIORITISE — Longer Booking Lead Times

Use Booking Lead Time as the primary signal for targeted attendance-support testing.

**Action:** Test proactive support for prioritised appointments.  
**Monitor:** No-Show Rate in the tested population.

#### 2 | REFINE — Recorded Previous No-Shows

Use Recorded Previous No-Shows as a complementary signal to refine prioritisation, subject to patient-history data-quality limitations.

**Action:** Test additional support for combined-priority appointment groups.  
**Monitor:** No-Show Rate by prioritisation profile.

#### 3 | TEST & MEASURE — Attendance Support

Test targeted reminder, confirmation or attendance-support approaches before wider deployment.

**Decision:** Extend, adjust or stop based on measured results.

### Guardrail

> **Prioritisation supports testing; it does not predict certain individual no-shows.**

---

# Week 7 Before / After Improvements

| Area | Before Week 7 Testing | Week 7 Refinement | Validated Outcome |
|---|---|---|---|
| Dashboard filters | Filtering could coexist with global conclusions | Tested context behaviour and separated page roles | Interactive vs validated views explicit |
| Decision signal | Static global signal on interactive page | Removed | No misleading static signal |
| Reminder comparison | Static comparison vulnerable to filter context | Removed from inappropriate interactive context | Context-consistent MONITOR |
| Recommendations | Action-oriented | Added explicit evaluation cycle | Decision → Action → KPI → Evaluation → Extend / Adjust / Stop |
| Lead × Appointment Type | Descriptive Follow-up gap could attract overinterpretation | Formal interaction test | No separate Follow-up rule |
| `long_lead_followup` | Candidate engineered Data Science feature | Controlled cross-track ablation | Removed |
| Distance | Weak standalone Analytics signal | Cross-track multivariable validation | Retained as model feature; Analytics classification unchanged |

---

# Data Analytics × Data Science Cross-Track Testing

Week 7 moved the Analytics × Data Science collaboration from integration to **controlled testing and refinement**.

**Data Analytics:** Nancy Lee YIMBERE ALAPINI  
**Data Science:** AYDEN NGNINTEDEM DEMANOU  
**Pod:** HC-POD 01

The cross-track dependency was:

> Validate Analytics findings that influence model features or modelling decisions.

Two explicit testing questions were submitted to Data Science.

---

## CT01 — `long_lead_followup`

### Testing Question

Does the engineered `long_lead_followup` feature provide measurable incremental out-of-sample predictive value beyond the broader Booking Lead Time signal?

### Test

Controlled with-vs-without feature ablation using:

- the same Logistic Regression pipeline;
- the same patient-grouped split;
- the same preprocessing;
- single-split ROC-AUC;
- bootstrap confidence intervals;
- grouped 5-fold cross-validation.

### Result

- Single-split AUC difference: **+0.0017**
- Bootstrap 95% CI: **[-0.0008, 0.0041]**
- Grouped 5-fold CV mean difference: **+0.0009**

The evidence did not demonstrate statistically meaningful incremental predictive value.

### Decision

> **REMOVE `long_lead_followup` FROM THE WEEK 8 CANDIDATE FEATURE SET**

### Validation Status

**TESTED → REFINED → RETESTED → VALIDATED**

---

## CT02 — `distance_to_clinic_km`

### Testing Question

Can Distance to Clinic provide incremental multivariable predictive value even though its standalone Analytics association is very weak?

### Result

- Analytics standalone association: **ρ ≈ 0.055**
- Single-split bootstrap CI: **[-0.0089, 0.0096]**
- Model with Distance outperformed model without Distance in **5/5 grouped CV folds**
- Mean grouped-CV difference: **+0.0043**
- Top-20%-risk lift: **1.44× with Distance vs 1.40× after removal**

### Decision

> **RETAIN `distance_to_clinic_km` AS A MODEST MULTIVARIABLE PREDICTIVE FEATURE**

This does not change its Data Analytics classification as **Secondary / Contextual** and does not justify standalone operational targeting.

### Validation Status

**TESTED → RETESTED → RETAINED**

---

## Cross-Track Learning

The Week 7 collaboration reinforced an important analytical distinction:

> **Standalone analytical differentiation ≠ Multivariable predictive contribution ≠ Causality**

A weak standalone Analytics relationship does not necessarily imply zero multivariable predictive contribution.

Conversely, feature importance or model usage does not automatically establish unique predictive value, business importance or causality.

### Cross-Track Evidence

[View HC-POD Cross-Track Evidence](reports/WK7_HealthConnect_HC-POD_Cross-Track_Evidence_Nancy_Lee_YIMBERE_ALAPINI.pdf)

[View DA × DS Cross-Track Testing & Validation Evidence](notebooks/WK7_HealthConnect_DA_DS_Cross-Track_Testing_Validation_Evidence.pdf)

---

# Week 7 Updated Business Insights

Week 7 validation confirmed that Booking Lead Time remains HealthConnect's strongest standalone analytical differentiation of No-Show behaviour, while Recorded Previous No-Shows provides complementary prioritisation information.

The combined evidence supports **group-level prioritisation for further attendance-support evaluation**, rather than deterministic individual prediction.

Reminder Status and Distance remain secondary or contextual factors and do not independently justify operational targeting.

Robustness testing further showed that the Lead-Time pattern persists across Appointment Types without establishing a distinct Appointment-Type interaction.

Cross-track testing strengthened this interpretation by showing that:

- `long_lead_followup` did not provide meaningful incremental predictive value and could be removed;
- Distance could remain useful inside a multivariable predictive model despite weak standalone Analytics differentiation.

---

# Week 7 Updated Recommendations

## 1 | PRIORITISE — Longer Booking Lead Times

Use longer-lead appointment groups as the primary population for further attendance-support evaluation.

**Monitoring KPI:** No-Show Rate within the evaluated longer-lead population.

---

## 2 | REFINE — Recorded Previous No-Shows

Use Recorded Previous No-Shows cautiously as complementary information when refining the population selected for evaluation.

**Monitoring KPI:** No-Show Rate by Recorded Previous No-Show status within the evaluated population.

---

## 3 | TEST & MEASURE — Attendance-Support Strategy

Test reminder, confirmation or other attendance-support interventions before wider deployment.

**Evaluation principle:**

> Measure improvement relative to a predefined evaluation reference.

### Decision Cycle

**VALIDATED EVIDENCE → DECISION → ACTION → MONITORING KPI → EVALUATION → EXTEND / ADJUST / STOP**

---

# Interpretation & Decision Guardrails

## Association ≠ Causality

Observed differences and statistical associations do not demonstrate causal effects.

## Predictive Relevance ≠ Causal Importance

A variable that contributes to a predictive model is not automatically a causal mechanism or an operational intervention target.

## Standalone Analytics ≠ Multivariable Predictive Contribution

A variable may show weak standalone differentiation while still contributing modestly within a multivariable model.

## Statistical Significance ≠ Business Significance

Results are interpreted alongside:

- effect size;
- robustness;
- sample size;
- operational relevance;
- decision usefulness.

## Benchmark ≠ Target

The overall No-Show Rate of **51.15%** is an internal descriptive reference.

It is not an external benchmark or performance target.

## Reminder Exposure ≠ Reminder Effectiveness

`reminder_sent = Yes` indicates recorded reminder exposure.

It does not prove that the reminder was:

- received;
- read;
- understood;
- acted upon;
- responsible for the appointment outcome.

## Recorded Patient History ≠ Verified Longitudinal History

Recorded Previous No-Shows is analytically useful but remains subject to patient-level consistency limitations.

## Prioritisation ≠ Deterministic Prediction

The decision-support framework identifies appointment groups for support and testing.

It does not classify individual patients as certain future no-shows.

---

# Week 7 End-to-End Validation

The final Analytics solution was validated across the full decision-support chain:

**DATA → POPULATION → KPI → ANALYTICAL FINDINGS → EVIDENCE HIERARCHY → BUSINESS INSIGHTS → DECISION SUPPORT → DASHBOARD → RECOMMENDATIONS → CROSS-TRACK VALIDATION → WEEK 8 READINESS**

| Validation Layer | Result |
|---|---|
| Data → Population | **PASS** |
| Population → KPI | **PASS** |
| KPI → Findings | **PASS** |
| Findings → Evidence Hierarchy | **PASS** |
| Evidence → Business Insights | **PASS** |
| Insights → Decision Support | **PASS** |
| Decision Support → Dashboard | **PASS** |
| Dashboard → Recommendations | **PASS** |
| Recommendations → Evaluation Cycle | **PASS** |
| Analytics → Data Science | **PASS** |
| Cross-Track → Solution Refinement | **PASS** |
| Guardrails & Interpretation | **PASS** |

### End-to-End Outcome

> **No critical unresolved Analytics inconsistency was identified.**

---

# Assumptions, Limitations & Remaining Risks

## Analytical Unit

The appointment record remains the validated analytical unit.

## Patient History

Reliable longitudinal patient histories cannot be reconstructed from the available dataset.

## Missing Values

Distance and Waiting Time contain a small proportion of missing observations.

## Sparse Segments

Some extreme categories have limited sample sizes and are interpreted cautiously.

## Observational Design

The current analysis supports differentiation, prioritisation and further testing — not causal conclusions.

## Intervention Effectiveness

The effectiveness of any attendance-support intervention remains unvalidated.

Therefore:

> **TEST → MEASURE → COMPARE → DECIDE**

## Dashboard Governance

The Power BI file remains editable.

Validated page behaviour and interpretation guidance should therefore be preserved during future implementation.

---

# Week 8 Readiness

Following Week 7 testing, refinement, retesting and cross-track validation, the HealthConnect Data Analytics workstream is ready for Week 8 integration.

## What is now validated?

- core KPI definitions and denominators;
- analytical evidence hierarchy;
- Booking Lead Time as the primary standalone signal;
- Recorded Previous No-Shows as complementary evidence;
- secondary/contextual classification of Reminder Status and Distance;
- combined-signal decision-support framework;
- Power BI values and page architecture;
- dashboard interaction guidance;
- business insights;
- recommendations;
- monitoring and evaluation cycle;
- Analytics × Data Science interpretation;
- removal of `long_lead_followup`;
- retention of Distance in the multivariable model.

## What remains uncertain?

Primarily:

- intervention effectiveness;
- longitudinal patient-history reliability;
- interpretation of sparse extreme segments;
- causal mechanisms beyond the observed associations.

## What must be completed before final integration and presentation?

- preserve the validated evidence hierarchy;
- preserve non-causal and non-deterministic guardrails;
- integrate Analytics and Data Science without conflating their evidence types;
- maintain Test & Measure for attendance-support interventions;
- carry forward documented limitations;
- maintain consistency across final reports, dashboard, evidence packs, GitHub and presentation.

### Week 8 Readiness Status

> **DATA ANALYTICS READY FOR WEEK 8 INTEGRATION**

No unresolved Week 7 Data Analytics → Data Science testing dependency remains.

---

# Week 7 Deliverables

| Deliverable | Access |
|---|---|
| Analytics Testing & Refinement Report | [Open PDF](reports/WK7_HealthConnect_Analytics_Testing_Refinement_Report_Nancy_Lee_YIMBERE_ALAPINI.pdf) |
| Week 7 Project Summary | [Open PDF](reports/WK7_HealthConnect_Project_Summary_Nancy_Lee_YIMBERE_ALAPINI.pdf) |
| Testing & Validation Evidence Pack | [Download Excel](analysis/WK7_HealthConnect_Testing_Validation_Evidence_Pack_Nancy_Lee_YIMBERE_ALAPINI.xlsx) |
| Power BI Dashboard | [Download PBIX](dashboards/WK7_HealthConnect_Analytics_Dashboard_Nancy_Lee_YIMBERE_ALAPINI.pbix) |
| HC-POD Cross-Track Evidence | [Open PDF](reports/WK7_HealthConnect_HC-POD_Cross-Track_Evidence_Nancy_Lee_YIMBERE_ALAPINI.pdf) |
| DA × DS Cross-Track Testing Evidence | [Open PDF](notebooks/WK7_HealthConnect_DA_DS_Cross-Track_Testing_Validation_Evidence.pdf) |

---

# Repository Structure

    healthconnect-experience-lab/
    │
    ├── analysis/
    │   └── WK7_HealthConnect_Testing_Validation_Evidence_Pack_Nancy_Lee_YIMBERE_ALAPINI.xlsx
    │
    ├── assets/
    │   └── week7/
    │       ├── WK7_HealthConnect_Dashboard_01_MONITOR_Performance_Overview.png
    │       ├── WK7_HealthConnect_Dashboard_02_DIAGNOSE_No-Show_Differentiation.png
    │       └── WK7_HealthConnect_Dashboard_03_PRIORITIZE_Attention_Priorities.png
    │
    ├── dashboards/
    │   └── WK7_HealthConnect_Analytics_Dashboard_Nancy_Lee_YIMBERE_ALAPINI.pbix
    │
    ├── notebooks/
    │   └── WK7_HealthConnect_DA_DS_Cross-Track_Testing_Validation_Evidence.pdf
    │
    ├── reports/
    │   ├── WK7_HealthConnect_Analytics_Testing_Refinement_Report_Nancy_Lee_YIMBERE_ALAPINI.pdf
    │   ├── WK7_HealthConnect_HC-POD_Cross-Track_Evidence_Nancy_Lee_YIMBERE_ALAPINI.pdf
    │   └── WK7_HealthConnect_Project_Summary_Nancy_Lee_YIMBERE_ALAPINI.pdf
    │
    └── README.md

---

# Week 7 Final Validation Status

**14 Analytics tests completed**

**Core KPIs revalidated**

**Analytical evidence hierarchy validated**

**Dashboard interpretation issue identified, refined and retested**

**Recommendations refined and validated**

**Meaningful Data Analytics × Data Science testing completed**

**Cross-track feature decisions implemented**

**End-to-end Analytics validation completed**

**No critical unresolved Analytics inconsistency identified**

**No open Week 7 Analytics → Data Science testing dependency**

> **FINAL STATUS: WEEK 7 PASS | READY FOR WEEK 8 INTEGRATION**

---

# Week 8 — Final Integration Focus

Week 8 should move from validated analytical and predictive components toward final HealthConnect solution integration.

The priority is not to reopen validated Week 7 findings without evidence.

The focus should be to:

1. integrate validated Analytics and Data Science outputs;
2. preserve the distinction between descriptive, predictive and causal evidence;
3. translate validated findings into a coherent final HealthConnect decision-support story;
4. retain the Test & Measure framework for attendance-support interventions;
5. maintain traceability from evidence to recommendation;
6. complete final cross-deliverable quality assurance;
7. prepare the final integrated presentation.

---

## Contributors

**Nancy Lee YIMBERE ALAPINI**  
Data Analytics — Performance & Decision Intelligence

**AYDEN NGNINTEDEM DEMANOU**  
Data Science — HC-POD 01 Cross-Track Collaboration

---

## Languages

**Python · SQL · DAX**

## Analytics & BI

**Power BI · Excel · Pandas · Statistical Validation · Decision Support**

---

*HealthConnect Experience Lab — AnalystLab Africa Internship Programme*
