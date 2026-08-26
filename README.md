# HealthConnect Experience Lab

## Improving Patient Appointment Attendance and Healthcare Support Using Data and AI | Data Analytics Track

**Data Analytics Track | AnalystLab Africa Internship Programme**

**Author:** Nancy Lee YIMBERE ALAPINI  
**Professional Focus:** Performance & Decision Intelligence Analyst  
**Project Status:** Week 4 — Analytical Foundation Completed

---

## 1. Project Overview

The **HealthConnect Experience Lab** is a multidisciplinary project developed as part of the AnalystLab Africa Internship Programme.

From Week 4 onward, interns across Data Analytics, Data Science, Machine Learning Engineering, Generative AI, and Project Management contribute to a shared healthcare business problem from their respective professional perspectives.

HealthConnect Clinic faces challenges related to missed appointments, cancellations, and patient support needs.

The broader project question is:

> **How can HealthConnect Clinic use data and AI to reduce missed appointments and improve the patient support experience?**

For the **Data Analytics Track**, the focus is to understand the appointment data and determine how it can be used to investigate appointment attendance and no-show patterns.

---

## 2. Project Continuity

The HealthConnect Experience Lab is a **progressive multi-week project**.

Each subsequent internship stage will build on the analytical foundation established during Week 4.

The overall project journey is expected to progress through:

**Problem Understanding → Analysis & Solution Design → Development → Testing & Refinement → Final Presentation**

This repository will therefore be updated progressively as the project advances.

---

# WEEK 4 — ANALYTICAL FOUNDATION

## 3. Week 4 Objective

Week 4 focuses on **understanding, reviewing, defining, and planning** rather than executing the full analysis.

The Data Analytics objective is to:

- understand the HealthConnect appointment dataset;
- review the Data Dictionary;
- assess initial data quality;
- identify variables relevant to appointment attendance and no-shows;
- define relevant Business Questions;
- identify potential KPIs linked to decision needs;
- formulate an initial analytical approach;
- document assumptions, limitations, risks, and dependencies.

No final explanation of no-show drivers is claimed at this stage.

> **Week 4 principle:**  
> **UNDERSTAND → REVIEW → DEFINE → PLAN**

---

## 4. Data Resources

Two project resources are used for the Data Analytics Track:

| Resource | Purpose |
|---|---|
| `HealthConnect_Appointment_Data.csv` | Fictional and anonymized appointment-level dataset |
| `HealthConnect_Data_Dictionary.xlsx` | Reference definitions for the variables contained in the dataset |

The original project resources are preserved unchanged.

---

## 5. Dataset Overview

The Data Dictionary was reviewed before analytical planning and used as the primary reference for understanding the dataset structure.

| Item | Result | Interpretation |
|---|---:|---|
| Number of rows | 5,000 | Each row represents one appointment |
| Number of columns | 18 | Consistent with the Data Dictionary |
| Analytical grain | Appointment record | Selected unit of analysis |
| `appointment_id` | 5,000 unique values | No duplicate appointment identifiers |
| `patient_id` | 1,696 unique values | May appear across multiple appointments |
| Appointment period | 01 Jan 2025 – 30 Jun 2026 | Scheduled appointment window |
| Primary outcome | Attended / No-Show / Cancelled | `appointment_outcome` |

The selected analytical grain is therefore the **appointment rather than the patient**.

This distinction is important because some attributes associated with repeated `patient_id` values are not longitudinally stable in the dataset.

---

## 6. Initial Data Quality Assessment

Technical inspection was performed before defining the future analytical execution.

| Check | Result | Assessment | Analytical Handling |
|---|---|---|---|
| Structure | 5,000 × 18; all expected variables present | PASS | Retain schema |
| `appointment_id` | 5,000 unique; 0 duplicates | PASS | Appointment-level grain confirmed |
| Dates / Lead Time | 0 invalid booking chronology; 0 lead-time mismatches; 0 appointment-day mismatches | PASS | Convert date fields before analysis |
| Reminder Channel | 1,366 missing values, all associated with `reminder_sent = No` | STRUCTURAL N/A | Treat as Not Applicable |
| `distance_to_clinic_km` | 90 missing values (1.8%) | ATTENTION | Assess handling before BQ4; no automatic imputation |
| `waiting_time_minutes` | 60 missing values (1.2%) | ATTENTION | Assess handling before BQ4; no automatic imputation |
| Internal History | 0 rows where `previous_no_shows > previous_appointments` | PASS | Logical row-level relationship respected |
| Repeated `patient_id` | Inconsistencies observed in demographic and historical attributes | LIMITATION | Avoid unreliable longitudinal reconstruction |

### Key Data Quality Implication

The dataset is sufficiently usable for the planned **appointment-level analysis**, but patient-level longitudinal interpretation requires caution.

---

## 7. Analytical Architecture

Variables were not selected simply because they were available.

They were organized according to their expected contribution to the Business Questions.

| Analytical Architecture | Variables | Analytical Role | BQ |
|---|---|---|---|
| Outcome / Baseline | `appointment_outcome` | Core outcome variable | BQ1 |
| Appointment Context | `appointment_type` | Compare patterns by appointment type | BQ2 |
| Scheduling Context | `appointment_day`, `appointment_time`, `booking_lead_days` | Examine scheduling-related differences | BQ2 |
| Reminder & Engagement | `reminder_sent`, `reminder_channel` | Examine patterns associated with reminders | BQ3 |
| Accessibility & Operations | `distance_to_clinic_km`, `waiting_time_minutes` | Examine accessibility and operational context | BQ4 |
| Recorded History | `previous_appointments`, `previous_no_shows` | Explore recorded history cautiously | BQ5 |
| Recorded Characteristics | `age`, `age_group`, `gender` | Appointment-level descriptive segmentation | BQ6 |
| Structural Support | `appointment_id`, `patient_id`, `booking_date`, `appointment_date` | Validation, grain, derivations, and traceability | Support |

---

## 8. Business Questions

The Week 4 analytical foundation is structured around six Business Questions.

| BQ | Business Question |
|---|---|
| **BQ1 — Overall Appointment Outcome** | What is the overall distribution of appointment outcomes, and what is the relative extent of no-shows? |
| **BQ2 — Appointment & Scheduling Context** | How do no-show patterns vary across appointment types and scheduling characteristics, including appointment day, appointment time, and booking lead time? |
| **BQ3 — Reminder & Engagement** | How do no-show patterns vary by reminder status and, where applicable, by the reminder channel used? |
| **BQ4 — Accessibility & Operational Context** | How do no-show patterns vary across recorded distance-to-clinic and estimated waiting-time levels? |
| **BQ5 — Recorded Patient History** | How do no-show patterns vary according to the recorded number of previous appointments and previous no-shows? |
| **BQ6 — Recorded Patient Characteristics** | How do no-show patterns vary across recorded age groups and gender categories? |

These questions define the analytical direction for subsequent project stages.

---

## 9. Analytical Hypotheses — Value-Added Layer

To move beyond unstructured exploratory analysis, the Business Questions were translated into explicit analytical hypotheses.

These hypotheses represent **relationships to be tested**, not established findings.

| Hypothesis | Focus | Relationship to Test |
|---|---|---|
| H2a | Appointment Type | The no-show rate differs across appointment types. |
| H2b | Appointment Day | The no-show rate differs across appointment days. |
| H2c | Appointment Time | The no-show rate differs across appointment time periods. |
| H2d | Booking Lead Time | No-show patterns differ according to the time between booking and appointment. |
| H3a | Reminder Sent | The no-show rate differs between appointments with and without a recorded reminder. |
| H3b | Reminder Channel | Among appointments with a reminder, the no-show rate differs across reminder channels. |
| H4a | Distance to Clinic | No-show patterns differ according to the recorded distance to the clinic. |
| H4b | Waiting Time | No-show patterns differ according to estimated waiting time. |
| H5a | Previous Appointments | No-show patterns differ according to the recorded number of previous appointments. |
| H5b | Previous No-Shows | No-show patterns differ according to the recorded number of previous no-shows. |
| H6a | Age Group | The no-show rate differs across recorded age groups. |
| H6b | Gender | The no-show rate differs across recorded gender categories. |

**BQ1 is descriptive and therefore does not require a formal analytical hypothesis.**

---

## 10. Business Question → Hypothesis → Analysis Map

The planned analysis follows a question-driven rather than chart-driven approach.

| Business Question | Focus | Hypotheses | Planned Analysis |
|---|---|---|---|
| BQ1 | Baseline | Descriptive | Outcome distribution and No-Show Rate after denominator definition |
| BQ2 | Appointment & Scheduling | H2a–H2d | Comparisons by appointment type, day, time period, and booking lead time |
| BQ3 | Reminder & Engagement | H3a–H3b | Reminder Yes vs No, followed by conditional comparison across reminder channels |
| BQ4 | Accessibility & Operations | H4a–H4b | Patterns across recorded distance and waiting time |
| BQ5 | Recorded History | H5a–H5b | Comparisons across recorded historical variables |
| BQ6 | Recorded Characteristics | H6a–H6b | Comparisons across age groups and gender categories |

---

## 11. Potential KPI Framework

Potential KPIs were selected using the following logic:

> **Business Question → Decision Need → Potential KPI**

rather than:

> Variable Available → Metric Calculable → KPI

Only three indicators were retained at this stage.

| Potential KPI | Linked BQ | Potential Decision Use | Week 4 Status |
|---|---|---|---|
| **No-Show Rate (%)** | BQ1 | Measure and subsequently monitor the relative magnitude of missed appointments | Potential KPI — denominator to be finalized |
| **Reminder Coverage Rate (%)** | BQ3 | Measure operational coverage of the reminder process | Potential KPI |
| **No-Show Rate by Reminder Status** | BQ3 | Compare no-show patterns between appointments with and without a recorded reminder | Potential diagnostic / decision-support KPI — association only |

Additional segmentation measures required for **BQ2–BQ6** will support the analysis but are **not automatically classified as KPIs**.

### Important Methodological Note

The **No-Show Rate will not be calculated until the eligible population, numerator, denominator, and treatment of Cancelled appointments are explicitly defined.**

---

## 12. Initial Analysis Approach

The future analysis will investigate no-show patterns progressively.

### Analytical Sequence

**Overall Outcome → Appointment & Scheduling → Reminder & Engagement → Accessibility & Operations → Recorded History → Recorded Characteristics**

### Proposed Methods

| Analytical Need | Proposed Method |
|---|---|
| Overall appointment profile | Frequencies and proportions |
| Categorical segment comparison | Counts, rates, cross-tabulations, and group-level comparisons |
| Continuous / ordinal variables | Distribution analysis followed by grouping only where justified |
| Reminder status | Comparison of No-Show Rates |
| Reminder channel | Conditional comparison where `reminder_sent = Yes` |
| Magnitude of differences | Absolute and relative differences where appropriate |
| Statistical evidence | Appropriate tests only where justified by the question, variable type, and assumptions |

No arbitrary segmentation of continuous variables will be applied before reviewing their distributions and analytical relevance.

---

## 13. Interpretation Principles

Future analytical interpretation will follow:

> **Finding → Interpretation → Business Implication → Recommendation**

Recommendations must be traceable to identifiable analytical evidence.

Because the dataset is observational:

> **Association ≠ Causation**

An observed relationship may justify further investigation, validation, or a pilot, but it will not automatically be interpreted as a causal effect.

---

## 14. Assumptions, Limitations, Risks & Dependencies

| Type | Key Consideration | Analytical Response |
|---|---|---|
| Assumption | Each row represents one appointment and `appointment_outcome` its recorded final status | Maintain appointment-level grain |
| Assumption | Historical variables may be used as recorded row-level information | Do not reconstruct longitudinal patient histories |
| Limitation | Demographic and historical inconsistencies exist across some repeated `patient_id` values | Limit patient-level conclusions |
| Limitation | Distance and waiting time contain limited missingness | Document handling before BQ4 |
| Limitation | Dataset is observational and limited to available variables | Do not infer causality or rule out unobserved determinants |
| Risk | Incorrect No-Show Rate denominator could alter interpretation | Define population, numerator, denominator, and formula first |
| Risk | Arbitrary grouping of continuous variables could create misleading patterns | Review distributions and justify analytical bands |
| Risk | Segmentation metrics could be incorrectly promoted to KPIs | Require a clear decision or monitoring need |
| Dependency | Final KPI and recommendation selection depends on future findings | Do not pre-select priority segments |
| Dependency | Cross-deliverable consistency requires stable metric definitions | Build a Metric Reference Table / Single Source of Truth before final reporting |

---

## 15. Hybrid Documentation Approach

Week 4 uses a hybrid documentation architecture:

**Raw Dataset → Technical Notebook → Validated Evidence → Initial Analysis Document → Future Analysis**

### Main Analytical Output

**Initial Analysis Document**

Provides the structured analytical communication layer:

- dataset understanding;
- data quality assessment;
- Business Questions;
- analytical hypotheses;
- potential KPIs;
- initial analysis approach;
- assumptions, limitations, risks, and dependencies.

### Supporting Technical Evidence

**Technical Data Inspection Notebook**

Provides reproducible evidence through:

> **Purpose → Code → Result → Interpretation**

The notebook validates dataset structure, data types, missing values, identifiers, consistency rules, and analytical readiness without prematurely answering the Business Questions.

---

## 16. Week 4 Deliverables

| Deliverable | Role |
|---|---|
| **Initial Analysis Document** | Main Data Analytics Week 4 analytical output |
| **Technical Data Inspection Notebook (.ipynb)** | Reproducible supporting technical evidence |
| **Technical Data Inspection Notebook (.pdf)** | Readable notebook export |
| **Week 4 Project Summary** | Concise project foundation summary |
| **Hybrid Documentation Approach** | Documentation architecture and traceability framework |

---

## 17. Repository Structure

```text
healthconnect-experience-lab/
│
├── README.md
│
├── week-4/
│   │
│   ├── reports/
│   │   ├── WK4_HealthConnect_Initial_Analysis_Document_...
│   │   ├── WK4_HealthConnect_Project_Summary_...
│   │   └── WK4_HealthConnect_Hybrid_Documentation_Approach_...
│   │
│   └── notebooks/
│       ├── WK4_HealthConnect_Technical_Data_Inspection_Notebook_....ipynb
│       └── WK4_HealthConnect_Technical_Data_Inspection_Notebook_....pdf
│
└── future-weeks/
    └── Project development will be added progressively
