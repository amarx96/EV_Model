# Data Directory

This directory contains the input data files for the EV infrastructure optimization model.

## Large Data Files (Not in Repository)

The following large data files are required but not included in the repository due to GitHub size limitations:

### Wind Data Files (~100+ MB each)
- `OffshoreWind.xlsx` - Offshore wind capacity data
- `ninja_wind_country_DE_current_merra-2_nuts-2_corrected(1).csv` - Current wind generation profiles
- `ninja_wind_country_DE_near-termfuture-merra-2_corrected.csv` - Near-term future wind profiles  
- `ninja_wind_country_DE_long-termfuture-merra-2_corrected.csv` - Long-term future wind profiles

### Load Data Files (~10+ MB each)
- `load.csv` - Hourly electricity load data
- `YearlyLoad.csv` - Annual load profiles

## Data Sources

- Wind data: [Renewables.ninja](https://renewables.ninja)
- Load data: Various German TSO sources
- Other data: Custom calculations and public datasets

## Usage

To run the model with full functionality, ensure these large data files are placed in this directory. Contact the authors for access to the complete dataset.

## Included Files

The repository includes smaller essential data files needed for model structure and testing.