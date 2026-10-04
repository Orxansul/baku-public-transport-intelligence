# baku-public-transport-intelligence
### ML-Based Passenger Demand, Anomaly Detection & Metro Disruption Analysis
End-to-end transport analytics project using Python, machine learning, geospatial analysis and Power BI to investigate passenger-demand shifts during a metro disruption.


## Project Overview

Baku Public Transport Intelligence is an end-to-end transport analytics case study investigating passenger-flow shifts during a temporary Baku metro disruption.

The project combines route-level demand modelling, machine learning, disruption impact analysis, robust demand-shock detection, bus–metro geospatial matching, station-level validation, coverage-gap analysis and Power BI visualization.

The objective is not to automatically recommend new routes, but to identify robust high-demand routes and screen potential express bus corridor candidates for further transport-planning investigation.


## Research Question

Which regular bus routes experienced robust excess passenger demand during the metro disruption, and where do these routes indicate potential corridor gaps relative to the metro network?


## Analytical Pipeline

Raw Data
↓
Data Quality & Coverage Assessment
↓
Expected Demand Modelling
↓
Actual Disruption Demand
↓
Excess Demand / Positive Shock
↓
Robust Route Detection
↓
Bus–Metro Spatial Matching
↓
Station-Level Validation
↓
Coverage Gap Analysis
↓
Corridor Screening
↓
Power BI Decision Dashboard


## Key Results

| Metric | Result |
|---|---:|
| Primary robust bus routes | 33 |
| High-demand unmet routes | 11 |
| Corridor screening candidates | 11 |
| Candidate/uncovered excess demand | ~189.8K |
| Normal-period validation MAPE | 2.15% |
| Strong station-support pairs | 58 |
| Moderate station-support pairs | 16 |
| M1–M6 demand coverage within 1000m | 80.15% |


## Methodology

### 1. Expected Demand

A route-specific Random Forest model estimates expected passenger demand using historical non-disruption observations.

### 2. Disruption Impact

Actual passenger demand during the disruption period is compared with model-based expected demand.

Excess demand is evaluated as the difference between actual and expected demand.

### 3. Robust Route Detection

Routes are retained when they demonstrate positive excess demand together with persistent positive demand shocks across the disruption observations.

### 4. Spatial Analysis

Robust bus routes are matched against available metro-route geometries using projected spatial distances and multiple proximity thresholds.

### 5. Station-Level Validation

Potential relationships are further assessed against metro station coordinates using 500 m and 1000 m spatial support thresholds.

### 6. Corridor Screening

Robust high-demand routes that remain insufficiently covered by the disruption-service metro corridors are retained as potential corridor-screening candidates.


## Limitations

- Passenger validations should not be interpreted as unique passengers.
- Metro station entries do not represent complete origin–destination journeys.
- Spatial proximity does not prove passenger transfer between a bus and a metro route.
- 500 m and 1000 m thresholds are analytical screening thresholds.
- The analysis does not establish causal effects from a simple before/after comparison.
- M7 and M9 are treated as later network context because they were introduced after the August passenger-demand observation window.
- The current M6 geometry cannot perfectly reconstruct every configuration during the full disruption period.
- Corridor candidates are screening results for further investigation, not automatic route-opening recommendations.


## Data Sources

The project uses publicly available transport data covering Baku bus passenger activity, metro passenger activity and public transport route geometries.

Source categories include:

- BakuBus passenger-flow data
- Baku Metro passenger-flow data
- AYNA public transport route geometry data
- Official AYNA announcements concerning metro disruption and supporting express routes


## Selected Results

<img width="2178" height="1294" alt="12J_08_evidence_funnel" src="https://github.com/user-attachments/assets/ccde4163-8349-4ce1-beb0-b7010d1b9f10" />
<img width="2603" height="1516" alt="12J_01_final_excess_demand" src="https://github.com/user-attachments/assets/e985ed3c-727d-4c77-b6eb-e734d3ed868b" />
<img width="2842" height="2396" alt="12J_09_final_baku_candidate_map" src="https://github.com/user-attachments/assets/6b2f3951-4ab9-4403-9d54-d284616cbd8d" />
<img width="1454" height="1296" alt="12J_07_bus_m_evidence_heatmap" src="https://github.com/user-attachments/assets/6157a707-a459-4830-9687-da06fb7e7e0c" />


## Power BI Dashboard

The final dashboard contains four analytical pages:

1. <img width="1419" height="806" alt="image" src="https://github.com/user-attachments/assets/e100b1c1-17cf-42fa-bd06-f4fc41cf8216" />

2. <img width="1335" height="759" alt="image" src="https://github.com/user-attachments/assets/6c866e58-c111-43ea-afc2-91a17fcd5013" />

3. <img width="1352" height="762" alt="image" src="https://github.com/user-attachments/assets/07bdfaf3-d2c3-4f9b-979e-5e7ce1503057" />

4. <img width="1351" height="765" alt="image" src="https://github.com/user-attachments/assets/7cb19c67-f60e-4749-a297-15521bcb9f00" />



## Project Links

- [Kaggle Dataset](https://www.kaggle.com/datasets/orxansuleymanov/baku-publick-transport-files)
- [Kaggle Notebook](https://www.kaggle.com/code/orxansuleymanov/baku-public-transport-intelligence/edit)
- [LinkedIn Case Study](https://www.linkedin.com/posts/xiiidelta_xiiidelta-datascience-transportanalytics-activity-7512578283734118400-EQCk?utm_source=share&utm_medium=member_desktop&rcm=ACoAAEnEo4cBum0enaGAuG6_VnioLhFaXT3jPjg)
- [Upwork Portfolio](https://www.upwork.com/freelancers/~01b5e3506436f6d4b1)

