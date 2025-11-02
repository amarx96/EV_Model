# Electric Vehicle Infrastructure Optimization Model

## Overview

This repository contains a comprehensive optimization model for electric vehicle (EV) infrastructure planning, developed as part of a seminar work at TU Berlin. The model focuses on optimizing the placement and sizing of EV charging infrastructure while considering various factors such as energy generation, storage systems, and commuting patterns.

## Project Structure

```
├── Dashboard/           # Interactive visualization dashboard
│   ├── src/
│   │   ├── Dashboard.jl       # Main dashboard application
│   │   ├── dash_functions.jl  # Dashboard utility functions
│   │   ├── helper_functions.jl # Helper functions
│   │   └── sankey.jl         # Sankey diagram implementation
│   ├── Project.toml     # Dashboard dependencies
│   └── colors.jl        # Color scheme definitions
├── Data/               # Input data files
│   ├── availability.csv      # Resource availability data
│   ├── Capex*.csv           # Capital expenditure data by year
│   ├── Demand.csv           # Energy demand data
│   ├── Distance.csv         # Distance matrices
│   ├── EmissionFactors.csv  # Emission factors
│   ├── EVCapShare.csv       # EV capacity sharing data
│   ├── Grid.csv             # Grid connection data
│   ├── MaxCap*.csv          # Maximum capacity constraints
│   ├── Regions.csv          # Regional data
│   ├── ResTech.csv          # Renewable energy technologies
│   ├── StorTech*.csv        # Storage technologies by year
│   └── VC*.csv              # Variable costs by year
├── Graphics/           # Output visualizations and plots
├── Project.toml        # Main project dependencies
├── Manifest.toml       # Dependency lock file
└── README.md          # This file
```

## Key Features

### 1. Multi-Technology Energy System Modeling
- **Renewable Energy Sources**: Solar PV, Wind (Onshore/Offshore), Hydro, Biomass
- **Conventional Generation**: Combined Cycle Gas Turbines (CCGT)
- **Storage Technologies**: Battery, Compressed Air, Hydrogen, Pumped Hydro Storage
- **Transmission Infrastructure**: Grid connections and capacity constraints

### 2. EV Integration Modeling
- **Commuting Patterns**: Detailed modeling of EV commuting between cities and rural areas
- **Charging Infrastructure**: Optimal placement and sizing of charging stations
- **Load Profiles**: Hourly EV charging demand patterns
- **Vehicle-to-Grid (V2G)**: Bidirectional energy flow capabilities

### 3. Interactive Dashboard
- Real-time visualization of optimization results
- Sankey diagrams for energy flow analysis
- Geographic mapping of infrastructure placement
- Scenario comparison tools

### 4. Temporal Resolution
- Hourly modeling for accurate load and generation profiles
- Seasonal variations (Summer/Winter scenarios)
- Multi-year investment planning (2025, 2035, 2045)

## Model Capabilities

The optimization model addresses several key research questions:

1. **Infrastructure Planning**: Where should EV charging stations be located?
2. **Capacity Sizing**: What are the optimal capacities for generation and storage?
3. **Technology Mix**: Which combination of technologies minimizes system costs?
4. **Grid Integration**: How does EV adoption impact the electricity grid?
5. **Emission Reduction**: What is the environmental impact of different scenarios?

## Technology Stack

- **Language**: Julia
- **Optimization**: Mathematical programming (likely JuMP.jl)
- **Visualization**: Dash.jl for interactive dashboards
- **Data Processing**: CSV.jl, DataFrames.jl

## Getting Started

### Prerequisites
- Julia 1.x
- Required packages (see Project.toml)

### Installation
1. Clone this repository
2. Navigate to the project directory
3. Install dependencies:
   ```julia
   using Pkg
   Pkg.activate(".")
   Pkg.instantiate()
   ```

### Running the Dashboard
```julia
cd("Dashboard")
using Pkg
Pkg.activate(".")
include("src/Dashboard.jl")
```

## Data Sources

The model incorporates various data sources:
- **Wind Data**: Renewables.ninja (MERRA-2 dataset)
- **Load Profiles**: Regional electricity consumption patterns
- **Technology Costs**: CAPEX and OPEX data for different years
- **Emission Factors**: Technology-specific emission coefficients
- **Geographic Data**: German NUTS-2 regions

## Results and Visualizations

The model generates comprehensive results including:
- Optimal technology mix by region and time period
- Investment schedules and capacity deployments
- Energy flow patterns (Sankey diagrams)
- Cost breakdowns and sensitivity analyses
- Environmental impact assessments

## Academic Context

This work is part of a seminar at TU Berlin focusing on operations research and optimization in energy systems. The model contributes to the understanding of:
- EV infrastructure planning under uncertainty
- Multi-objective optimization in energy systems
- Integration of renewable energy and electric mobility
- Spatial and temporal optimization challenges

## Contact

**Alexander Marx**  
Data Analyst & Energy Economist  
TU Berlin

## License

This project is developed for academic purposes as part of a seminar work at TU Berlin.

---

*For detailed methodology and results, please refer to the accompanying seminar paper.*