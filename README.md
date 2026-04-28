# FIFA World Cup 2026 - Travel Fatigue Analysis

> **Can travel fatigue influence match results at a World Cup?**  
> A data-driven analysis combining logistics, sports science, and statistics.

---

## Project Overview

This project analyzes the **travel burden** placed on national football teams competing at the **FIFA World Cup 2026** (USA, Canada, Mexico).

Using the scientifically validated **ECSS Protocol (Reilly et al., 2007)**, I calculate a **Travel Fatigue Index (TFI)** for each team - measuring the total recovery days needed due to travel distance, jetlag, and insufficient rest between matches.

The hypothesis is then **tested against real match data from WM 2022 (Qatar)** using Pearson correlation and an independent T-test.

---

##  Hypothesis

> **"Teams with a higher Travel Fatigue Index (TFI) perform worse in the group stage."**

Tested on FIFA World Cup 2022 data - because all 32 teams traveled to a single host country (Qatar), making it an ideal controlled environment.

---

## What's Analyzed

### Part 1 - TFI Forecast for WM 2026
- Base camp locations for 7 UEFA/CONMEBOL teams
- Full travel route: Home → Base Camp → Stadiums → Base Camp
- TFI components: distance fatigue + jetlag + recovery deficit

### Part 2 - Airport & Logistics Analysis
- Match load per airport across 16 host cities
- Regional distribution (East / Central / West / Mexico / Canada)
- Peak load phases (2 matches in the same city within ≤ 2 days)

### Part 3 - Hypothesis Testing on WM 2022 Data
- TFI calculated for all 32 teams (Doha as the central hub)
- Merged with real match results (points, goals, knockout qualification)
- Statistical validation: Pearson correlation + independent T-test

---

## Scientific Method

Jetlag calculation follows the **ECSS Protocol**:

| Direction | Recovery Days per Time Zone |
|-----------|----------------------------|
| Eastward  | 1.0 day / zone (harder)    |
| Westward  | 0.5 days / zone (easier)   |

> **Why the difference?**  
> The human circadian clock runs at ~24.2 hours - slightly longer than 24h.  
> Adapting to a *longer* day (westward travel) is natural.  
> Adapting to a *shorter* day (eastward travel) goes against biology.

**TFI Formula:**
```
TFI (days) = (Distance_km / 1000 × 0.5) + Jetlag_days + Recovery_deficit
```

**Recovery deficit** = shortfall below the FIFA-standard 3-day minimum rest between matches.

> Source: Reilly T. et al. (2007). *Travel fatigue and jet-lag in professional sport.*  
> Clinics in Sports Medicine, 26(3), 491-505.

---

## Tech Stack

| Tool | Purpose |
|------|---------|
| Python 3.x | Core language |
| Pandas | Data loading & transformation |
| NumPy | Numerical calculations |
| Matplotlib | All visualizations |
| Geopy (`geodesic`) | Geodetic distance calculation |
| SciPy (`stats`) | Pearson correlation & T-test |

---

## Data Sources

| Dataset | Source |
|---------|--------|
| FIFA World Cup 2026 Match Data | [Kaggle - areezvisram12](https://www.kaggle.com/datasets/areezvisram12/fifa-world-cup-2026-match-data-unofficial) |
| FIFA World Cup 2022 Complete Dataset | [Kaggle - die9origephit](https://www.kaggle.com/datasets/die9origephit/fifa-world-cup-2022-complete-dataset) |

> CSV files are not included in this repository.  
> Please download the datasets directly from Kaggle using the links above.

---

## Visualizations

### Travel Fatigue Index - Recovery Days per Team
![TFI Ranking](images/TFI_Recovery_Days_per_Team_.png)

### TFI Components Breakdown (Distance + Jetlag + Recovery Deficit)
![TFI Components](images/TFI_Components.png)

### Jet Lag Burden by Team (ECSS Protocol)
![Jet Lag](images/Jet_Lag_Burden.png)

### Matches per Airport - Total Tournament Load
![Airport Load](images/Matches_per_Airport.png)

### Match Distribution by Region
![Match Distribution](images/Match_Distribution.png)

### Airport Peak Operational Pressure
![Peak Phases](images/Airport_Peak_Operational_Pressure.png)

### Hypothesis Analysis - TFI vs. WC 2022 Results
![Hypothesis](images/Hypothesis_Analysis.png)
---

## Repository Structure

```
fifa-wc2026-travel-fatigue/
├── README.md
├── fifa-wc-2026.ipynb
├── LICENSE
├── requirements.txt
└── images/
    ├── TFI_Recovery_Days_per_Team_.png
    ├── TFI_Components.png
    ├── Jet_Lag_Burden.png
    ├── Matches_per_Airport.png
    ├── Match_Distribution.png
    ├── Airport_Peak_Operational_Pressure.png
    └── Hypothesis_Analysis.png
```

---

## How to Run

1. Clone the repository:
```bash
git clone https://github.com/AndriiSemenof/fifa-wc2026-travel-fatigue.git

```

2. Install dependencies:
```bash
pip install -r requirements.txt
```

3. Download datasets from Kaggle (links above) and place CSV files in the project root directory.

4. Open and run the notebook:
```bash
jupyter notebook fifa-wc2026.ipynb
```

---

## Requirements

```
pandas
numpy
matplotlib
geopy
scipy
```

---
