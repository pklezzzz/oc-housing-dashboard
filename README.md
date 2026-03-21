# Orange County Housing Justice Dashboard

**By Paxton Wang** · 2026

An interactive data science project mapping the gap between housing need and supportive housing resource availability across Orange County, California.

## What This Does

Using HUD Housing Inventory Count (HIC) 2025 data merged with Census ACS and CalEnviroScreen 4.0, this dashboard:

- Calculates a **Composite Need Score** for each census tract based on rent burden, income need, and poverty rate
- Identifies **18 critically underserved tracts** — high need, insufficient beds
- Maps all 75 analyzed tracts interactively with toggleable layers
- Shows correlations between housing variables
- Provides city-level and tract-level breakdowns

## Key Findings

- **18 of 75 analyzed tracts** are critically underserved (above-median need, below-median beds)
- **Rent burden and bed counts are negatively correlated (r = −0.243)** — the areas that need housing most have the fewest resources
- **6 underserved tracts have zero beds** despite need scores above 0.808
- Anaheim and Santa Ana have the highest concentration of underserved tracts

## Need Score Formula

```
Need Score = (Rent Burden × 0.40) + (Income Need × 0.25) + (Poverty Percentile × 0.35)
```

CalEnviroScreen 4.0 is displayed as a separate map layer and is not included in the formula to avoid double-counting population vulnerability.

## Data Sources

| Source | Description |
|--------|-------------|
| HUD HIC 2025 (HDX) | 263 OC supportive housing programs |
| Census ACS 5-Year | Median household income by tract |
| HUD CHAS | Rent burden %, poverty rate by tract |
| CalEnviroScreen 4.0 | Cumulative environmental burden by tract |
| Census TIGERweb 2020 | Tract centroid coordinates (482 OC tracts) |

## Run Locally

```bash
# Install dependencies
pip install -r requirements.txt

# Run dashboard
streamlit run oc_housing_dashboard.py
```

Make sure `HousingCentersOC.xlsx` is in the same folder as `oc_housing_dashboard.py`.

## Files

```
oc_housing_dashboard.py   ← Main dashboard
HousingCentersOC.xlsx     ← Data file (HUD HIC + census enrichment)
requirements.txt          ← Python dependencies
```

## Contact

Paxton Wang · paxtonmwang@gmail.com
