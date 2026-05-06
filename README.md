# Stormont Vail Health – Critical Patient Experiences

> **2026 ASA DataFest — Best Visualization Award 🏆**  
> An analysis of critical patient journeys to surface care gaps, demographic disparities, and escalation patterns across Stormont Vail Health's Kansas network.

*By Tran Nguyen, Parfait Ngandu, Ben Carr*

---

## Project Description

This project was developed for **ASA DataFest 2026** using real-world patient encounter data provided by **Stormont Vail Health**, a regional health system based in Kansas. The goal was to explore the patient journey — from initial diagnosis through follow-up care — and identify where the system is falling short for its most vulnerable patients.

The analysis is organized into three interconnected parts:

1. **Underserved Communities** — mapping where Stormont Vail's departments are relative to where Kansas populations actually live
2. **Disparities in Emergency Follow-Up Timing** — identifying whether same-day follow-up rates differ across racial/ethnic demographics
3. **Severe Diagnoses and Care Escalation** — examining how delays in follow-up correlate with worsening patient outcomes

The project was recognized with the **Best Visualization award** at DataFest 2026.

---

## Dataset

**Source:** Real-world patient encounter data provided by Stormont Vail Health via ASA DataFest 2026 (confidential/competition use only).

**Supplemental:** Kansas Population by County 2025 (for geographic gap analysis).

>  Raw data is not included in this repository as it is proprietary and was provided exclusively for DataFest competition use.

---

##  Analysis Overview

### Part 1 — Underserved Communities & Opportunities for Expansion

Using department location data overlaid against Kansas county population maps, the team identified a critical geographic mismatch: **Stormont Vail's departments are heavily clustered in the Northeast**, while high-population counties in other regions have little to no departmental presence. This points to clear opportunities for system expansion to reach underserved communities.

**Key finding:** There are high-population areas across Kansas — particularly outside the Northeast cluster — with zero Stormont Vail department coverage.

---

### Part 2 — Disparities in Emergency Follow-Up Timing

Emergency patients were analyzed for **same-day follow-up rates** broken down by racial/ethnic group. Pairwise comparisons across the top 10 race group combinations revealed notable differences in how quickly different demographics receive post-emergency care.

**Key finding:** Emergency patients had widely varied timely follow-up rates across demographics. Notable gaps include:
- Middle Eastern or North African patients vs. Native Hawaiian or other Pacific Islander: **+13.84 percentage point** difference in same-day follow-up
- Hispanic, Latino, or Spanish vs. White or Caucasian: **−6.74 percentage point** gap, suggesting Hispanic patients were less likely to receive same-day follow-up compared to White patients

These disparities suggest systemic inequities in post-emergency care access that warrant further investigation.

---

### Part 3 — Severe Diagnoses and How They Escalate

Time-to-next-encounter was analyzed for patients with **High Severity** and **Critical Severity** diagnoses, segmented by whether their next visit represented a de-escalation, same-level, or escalated care setting (e.g., Outpatient → Hospital Inpatient).

Box plots (trimmed at 95th percentile = 146 days) revealed a clear pattern: **patients whose next visit escalated to a more critical care setting had substantially higher variance and longer wait times** before that next encounter.

**Key findings:**
- Severe conditions require timely care — delays directly correlate with worsening outcomes
- When patients weren't seen promptly, their care setting escalated (e.g., from outpatient to inpatient hospitalization)
- Inconsistent wait times — not just long ones — coincide with adverse outcomes, suggesting unpredictability in scheduling is itself a risk factor

---

## Summary of Findings

| Analysis Area | Key Insight |
|---|---|
| Geographic Coverage | Department locations cluster in Northeast Kansas; high-population areas elsewhere are underserved |
| Follow-Up Disparities | Same-day follow-up rates vary by up to ~14 percentage points across racial/ethnic groups |
| Care Escalation | Longer and more variable wait times after severe diagnoses predict escalation to higher-acuity care |
| Highest-risk scenario | Critical severity patients with delayed follow-up are most likely to escalate to inpatient settings |

---

## Tools & Methods

- **Data wrangling & analysis:** R / Python (pandas, dplyr)
- **Visualization:** ggplot2 / matplotlib / seaborn
- **Geographic mapping:** County-level choropleth maps of Kansas department locations vs. population density
- **Statistical comparison:** Pairwise race group comparisons for same-day follow-up rates
- **Survival/time analysis:** Box plots of time-to-next-encounter by severity level and visit transition type

---

## Project Structure

```
├── DataFestFinalPres.pdf     # Award-winning presentation poster
├── index.ipynb               # Analysis notebook (if applicable)
└── README.md                 # This file
```

---

## Team

| Name | Role |
|---|---|
| Tran Nguyen | Analysis & Visualization |
| Parfait Ngandu | Analysis & Visualization |
| Ben Carr | Analysis & Visualization |

---

## Recognition

> **2026 ASA DataFest — Best Visualization**  
> Stormont Vail Health Challenge

---

## 📌 Notes & Limitations

- Data was provided solely for DataFest competition purposes and cannot be redistributed.
- Patient-level data was anonymized per DataFest data use agreement.
- Geographic analysis used 2025 Kansas county population estimates as a proxy for demand.
- Time-to-encounter analysis was trimmed at the 95th percentile (146 days) to reduce the influence of extreme outliers.
- Pairwise demographic comparisons reflect the dataset provided and may not generalize to other health systems or regions.
