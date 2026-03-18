# Airdrie Population Projection

Monthly population forecast for Airdrie, AB through December 2027, using 2016/2021 StatCan census data and city building permit registries.

## What it does

Builds a monthly time series from census anchors (2011–2024), then forecasts forward using Prophet and XGBoost blended 60/40. Outputs include total population, gender split, and 5-year age-band breakdowns for every month in the forecast window.

## Data needed

Put these four files in the same folder as the notebook:

- `CensusProfile2016-*.csv` — from Statistics Canada
- `CensusProfile2021-*.csv` — from Statistics Canada
- `2023_Building_permit_YTD_registry.xlsx` — from City of Airdrie
- `1_Jan_building_permit_YTD_registry_xlsx.xlsx` — from City of Airdrie

## Setup

```
pip install pandas numpy matplotlib plotly prophet xgboost scikit-learn openpyxl jinja2
```

Tested on Python 3.9. If you're on pandas 2.0+ the notebook patches the `Int64Index` removal automatically.

## Running

Open `airdrie_population_projection_v5.ipynb` and run all cells. CSVs and charts save to the working directory.

## Caveats

Forecasts beyond ~18 months should be treated as directional. Migration shocks and economic conditions aren't modelled.
