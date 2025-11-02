# Data Documentation

## Overview
This document describes the structure and contents of the data files used in the EV infrastructure optimization model.

## Core Data Files

### Energy Demand
- `Demand.csv`: Annual energy demand by region
- `load.csv`: Hourly load factors
- `summerLoad.csv`: Summer season load profiles
- `winterLoad.csv`: Winter season load profiles
- `YearlyLoad.csv`: Annual load aggregation

### Technology Data

#### Generation Technologies
- `ResTech.csv`: Renewable energy technology parameters
- `ResMaxCap.csv`: Maximum renewable capacity constraints
- `ResMaxCapWithBiomass.csv`: Extended capacity including biomass

#### Storage Technologies
- `StorTech25.csv`: Storage technology parameters for 2025
- `StorTech35.csv`: Storage technology parameters for 2035
- `StorTech45.csv`: Storage technology parameters for 2045
- `StorCapex.csv`: Storage capital costs

#### Cost Data
- `Capex2025.csv`, `Capex2035.csv`, `Capex2045.csv`: Capital expenditures by year
- `VC2025.csv`, `VC2035.csv`, `VC2045.csv`: Variable costs by year

### Environmental Data
- `EmissionFactors.csv`: CO2 emission factors by technology
- `Emfactor2035.csv`: Future emission factors
- `Em2025.csv`, `Em2045.csv`: Emission data by scenario year

### Renewable Energy Resources
- `availability.csv`: General resource availability
- `RESavailabilitySummer.csv`: Summer renewable availability
- `RESavailabilityWinter.csv`: Winter renewable availability
- `ninja_wind_country_DE_*.csv`: Detailed wind resource data from Renewables.ninja

### Grid and Infrastructure
- `ElectricityGrid.csv`: Grid topology and capacity
- `Grid.csv`: Additional grid parameters
- `Distance.csv`: Inter-regional distances
- `Regions.csv`: Regional identifiers and characteristics

### Electric Vehicle Data
- `EVCity.csv`: Urban EV adoption scenarios
- `EVCountry.csv`: Rural EV adoption scenarios
- `EvCapShare.csv`: EV capacity sharing parameters
- `Commuters.csv`: Commuting flow data
- `CommuteCosts.csv`: Transportation cost data

### Capacity Constraints
- `MaxCap.csv`: General capacity limitations
- `MaxRexCap2.csv`: Extended capacity constraints
- `MaxStorCap20.csv`, `MaxStorCap30.csv`, `MaxStorCap40.csv`: Storage capacity limits

## Data Sources

### Renewable Energy Data
- **Renewables.ninja**: Wind and solar resource data
- **MERRA-2**: Meteorological reanalysis data
- **NUTS-2 Regions**: European statistical regions

### Technology Parameters
- **Industry Reports**: Technology cost and performance data
- **Academic Literature**: Efficiency and operational parameters
- **Government Statistics**: Regional energy consumption

### Transportation Data
- **Federal Statistical Office**: Commuting patterns
- **Transport Studies**: EV adoption scenarios
- **Infrastructure Mapping**: Charging station locations

## Data Quality and Validation

All data files have been validated for:
- Completeness and consistency
- Temporal alignment (hourly resolution)
- Spatial consistency (NUTS-2 regions)
- Unit standardization
- Outlier detection and handling

## Usage Notes

1. **File Formats**: All data files are in CSV format with headers
2. **Missing Values**: Handled through interpolation or default values
3. **Updates**: Data reflects latest available information as of project completion
4. **Preprocessing**: Some files may require preprocessing before model input

For specific column descriptions and data ranges, refer to the individual CSV files and their headers.