# Energy System Optimization with EV Battery Flexibility

## Technical University of Berlin - Seminar Paper
**Faculty VII (School of Economics and Management)**  
**Workgroup for Infrastructure Policy (WIP)**  
**Operations Research - Methods for Network Engineering**

### Authors
- **Alexander Marx** (0479352)
- **Lorenz Richter** (403607)

### Supervisors
- **Prof. Ph.D. Christian von Hirschhausen**
- **Ph.D. Karlo Hainsch**

---

## Abstract

Electric vehicles (EVs) present a unique opportunity to address renewable energy intermittency through their distributed battery storage capacity. This study develops an optimization framework to analyze how EV charging infrastructure and battery flexibility can enhance grid stability while supporting the transition to renewable energy sources in the German electricity system.

Our research focuses on the interconnection between Germany's urban and rural areas via EVs and Vehicle-to-Grid (V2G) technology, examining how commuting patterns between countryside and cities can provide valuable flexibility services to the power grid.

## Research Questions

1. **How can EV battery flexibility support renewable energy integration?**
2. **What is the optimal spatial distribution of charging infrastructure between rural and urban areas?**
3. **How do different temporal scenarios (2025, 2035, 2045) affect system optimization?**
4. **What are the economic and environmental benefits of coordinated EV charging and V2G services?**
5. **What role do commuting patterns play in providing grid flexibility?**

## Methodology

Our model employs a **mixed-integer linear programming (MILP)** approach to minimize total system costs while optimizing:

- **Power generation** by various technologies (renewable and conventional)
- **Transmission capacity** between regions and offshore wind connections
- **Electric vehicle deployment** and charging/discharging patterns
- **Storage systems** including batteries, pumped hydro, and hydrogen

### Key Model Features:
- **29 distinct regions**: 16 German states split into urban/rural areas (except city-states)
- **Multi-scenario analysis**: 2025, 2035, and 2045 projections
- **Temporal resolution**: Hourly optimization over representative summer/winter days
- **Spatial modeling**: Focus on commuter flows between countryside and cities
- **Technology integration**: Comprehensive representation of generation, storage, and transmission

### Objective Function:
```
min Σ [Generation Costs + Investment Costs + Transmission Costs + EV Costs + Storage Costs]
```

Subject to constraints for:
- Energy balance and demand satisfaction
- Renewable generation and capacity limits
- EV charging/discharging dynamics and availability
- Storage operation and capacity constraints
- CO₂ emission limitations

## Key Results & Visualizations

### 1. Technology Mix Evolution (2025 → 2035)

![Baseline Technology Mix](Graphics/technology_mix_baseline.png)
*Figure 1: Baseline energy production showing current technology composition with CCGT dominance (~80 GWh) and limited renewable integration*

![Technology Mix 2025](Graphics/technology_mix_2025.png)
*Figure 2: 2025 scenario demonstrating increased renewable penetration with significant CCGT (~45 GWh), emerging Biomass (~9 GWh), and growing wind/solar contributions*

![Technology Mix 2035](Graphics/technology_mix_2035.png)
*Figure 3: 2035 scenario showing further renewable expansion with reduced CCGT dependency (~45 GWh) and enhanced transmission infrastructure role*

**Key Insights:**
- **CCGT remains dominant** but with reduced capacity from 2025 to 2035
- **Renewable energy sources** show steady growth, particularly wind and solar
- **Transmission infrastructure** becomes increasingly critical for renewable integration
- **Biomass emerges** as an important dispatchable renewable source in 2025

### 2. Storage System Analysis

![Storage Technologies 2025](Graphics/storage_mix_2025.png)
*Figure 4: 2025 storage mix showing EV battery dominance (~3.5 GWh) as the primary flexibility provider, with supporting roles from stationary batteries and pumped hydro*

![Storage Technologies 2035](Graphics/storage_mix_2035.png)
*Figure 5: 2035 storage evolution with reduced EV contribution and increased stationary battery deployment (~11 GWh), indicating technology maturation and cost optimization*

**Key Insights:**
- **EV batteries provide significant value in 2025** (129 million EUR system value) when stationary storage is expensive
- **Technology transition by 2035**: Stationary batteries become cost-competitive, reducing EV system value to 0
- **Pumped hydro storage** maintains steady contribution across scenarios
- **Hydrogen storage** plays limited role in daily energy balancing

### 3. Spatial Distribution and Network Analysis

![German Network Topology](./Graphics/map.jpg)
*Figure 6: Model network showing 29 regions with transmission grid connections (yellow lines), EV commute routes (red lines), and population centers (green/blue circles) representing the spatial structure of the German energy system*

**Network Characteristics:**
- **Blue circles**: Metropolitan population centers and major cities
- **Green circles**: Rural population centers and smaller towns  
- **Yellow lines**: Electricity transmission grid connections
- **Red lines**: EV commuting routes between rural and urban areas
- **Black dots**: Additional cities and metropolitan regions

## Model Results Summary

### Scenario Comparison

| **Metric** | **2025** | **2035** | **Unit** |
|------------|----------|----------|----------|
| **EV System Value** | 129 | 0 | Million EUR |
| **EV Share in Commuting** | 10% | 50% | % of commuters |
| **Renewable Integration** | Medium | High | Qualitative |
| **CCGT Capacity** | ~45 | ~45 | GWh |
| **Storage Dominance** | EV Batteries | Stationary Batteries | Technology |

### Storage Technology Values (Million EUR)

| **Technology** | **2025** | **2035** |
|----------------|----------|----------|
| **EV Batteries** | 129.0 | 0.0 |
| **Stationary Batteries** | 7.9 | 15.4 |
| **Pumped Hydro** | 2.2 | 12.3 |
| **Hydrogen Storage** | 4.2 | 1.9 |

## Technical Implementation

### EV Integration Parameters
- **Energy Consumption**: 0.16 kWh/km (Taljegard et al., 2017)
- **Charging/Discharging Capacity**: 7.4 kW per vehicle
- **Battery Capacity**: 64 kWh per vehicle
- **Efficiency**: 90% roundtrip charging/discharging

### Commuting Patterns
- **Morning commute**: Countryside → City (peak 7-9 AM)
- **Evening return**: City → Countryside (peak 5-7 PM)
- **Availability profiles**: Dynamic based on mobility patterns
- **Geographic coverage**: All 16 German federal states

### Technology Cost Projections

| **Technology** | **2025** | **2035** | **2045** | **Unit** |
|----------------|----------|----------|----------|----------|
| **EV CapEx** | 2,806 | 2,336 | 1,866 | EUR/car/year |
| **Grid CapEx** | 2,266 | 2,383 | 2,331 | EUR/kW/year |
| **Battery Storage** | 515 | 202 | 92 | EUR/kW |
| **Offshore Wind** | 121 | 109 | 102 | EUR/kW |

## Key Findings

### 1. **EV Flexibility Value Diminishes Over Time**
- EVs provide substantial system value (129M EUR) in 2025 when stationary storage is expensive
- By 2035, improved stationary battery economics eliminate EV system value
- **Policy Implication**: Early EV adoption programs should emphasize grid services

### 2. **Spatial Energy System Transformation**
- Rural areas become renewable energy production centers
- Urban areas rely increasingly on transmission and storage
- **EV commuting** creates natural energy transport mechanism between regions

### 3. **Technology Transition Pathway**
- **2025**: EV-led flexibility with emerging renewables
- **2035**: Stationary storage dominance with high renewable penetration
- **Grid infrastructure** becomes critical bottleneck requiring expansion

### 4. **Emission Reduction Potential**
- Model incorporates German Federal Climate Change Act targets
- CO₂ budget: 220M tons (2025) → 110M tons (2035) → 0 tons (2045)
- EV integration supports decarbonization through renewable energy balancing

## Policy Implications

1. **Early EV Market Development**: Support V2G infrastructure when stationary storage costs are high
2. **Coordinated Infrastructure Planning**: Align charging infrastructure with renewable energy deployment
3. **Grid Modernization**: Expand transmission capacity for renewable energy integration
4. **Rural-Urban Energy Coordination**: Leverage commuting patterns for system-wide optimization

## Data Sources & Assumptions

### Key Datasets
- **Commuting data**: Pendlerrechnung der Länder (2022)
- **Renewable profiles**: Pfenninger and Staffell (2016) - 30 years validated data
- **Technology costs**: PyPSA technology database (Brown et al., 2017)
- **Emission factors**: Hamels (2021) and German Federal Climate Act

### Model Limitations
- **Representative days**: Single summer/winter day may not capture seasonal variations
- **Simplified charging behavior**: Assumes optimal coordination without behavioral constraints
- **Uniform EV adoption**: Does not account for socio-economic adoption patterns
- **Perfect foresight**: Optimization assumes complete information availability

## Future Research Directions

1. **Behavioral Integration**: Incorporate heterogeneous charging preferences and willingness to participate in V2G
2. **Multi-seasonal Analysis**: Extend temporal scope beyond representative days
3. **International Integration**: Model cross-border electricity trade and European coordination
4. **Uncertainty Analysis**: Robust optimization under deep uncertainty scenarios
5. **Sector Coupling**: Include heating and industrial demand interactions

## Installation & Usage

### Prerequisites
- Julia 1.8+
- Required packages (automatically installed via Project.toml)

### Getting Started
```julia
# Clone the repository
git clone https://github.com/amarx96/Energy-System-with-EV-Battery-Flexibility.git

# Navigate to project directory  
cd Energy-System-with-EV-Battery-Flexibility

# Activate project environment
julia --project=.

# Install dependencies
] instantiate

# Run optimization model
include("src/main.jl")

# Launch interactive dashboard
include("Dashboard/src/Dashboard.jl")
```

## Repository Structure

```
├── Dashboard/              # Interactive visualization dashboard
│   ├── src/
│   │   ├── Dashboard.jl    # Main dashboard application
│   │   ├── dash_functions.jl # Utility functions for visualizations
│   │   ├── sankey.jl       # Sankey diagram implementations
│   │   └── helper_functions.jl # Supporting utilities
│   └── colors.jl           # Color scheme definitions
├── Data/                   # Input datasets
│   ├── README_DATA.md      # Comprehensive data documentation
│   ├── Commuters.csv       # Inter-regional commuting patterns
│   ├── Regions.csv         # German federal state definitions
│   ├── Capex*.csv          # Technology cost projections by scenario
│   ├── EvCapShare.csv      # EV market penetration assumptions
│   └── ...                 # Additional model input files
├── Graphics/               # Research result visualizations
│   ├── technology_mix_*.png # Energy production analysis
│   ├── storage_mix_*.png   # Storage system comparisons
│   └── network_topology.png # Spatial model representation
├── Project.toml           # Julia package dependencies
├── Manifest.toml          # Exact package versions for reproducibility
├── METHODOLOGY.md         # Detailed mathematical formulation
└── DATA_DOCUMENTATION.md  # Complete data source documentation
```

## Academic Context

This research contributes to the growing literature on energy system flexibility and EV integration:

- **Novel spatial approach**: First study to explicitly model rural-urban EV commuting for grid services
- **Comprehensive technology comparison**: Direct economic comparison of EV vs. stationary storage
- **Policy-relevant scenarios**: Aligned with German climate targets and energy transition timeline
- **Methodological innovation**: Integration of mobility patterns with power system optimization

## Citation

```bibtex
@techreport{marx2025ev,
  title={Electric Vehicles as a Flexibility Option in the German Energy System},
  author={Marx, Alexander and Richter, Lorenz},
  institution={Technical University of Berlin, Faculty VII, Workgroup for Infrastructure Policy},
  year={2025},
  type={Seminar Paper},
  course={Operations Research - Methods for Network Engineering},
  supervisor={Hirschhausen, Christian von and Hainsch, Karlo}
}
```

## Contact Information

**Primary Authors:**
- **Alexander Marx**: [alex.marx@tu-berlin.de] - [@amarx96](https://github.com/amarx96)
- **Lorenz Richter**: [lorenz.richter@tu-berlin.de]

**Academic Supervisors:**
- **Prof. Ph.D. Christian von Hirschhausen** - Workgroup for Infrastructure Policy (WIP)
- **Ph.D. Karlo Hainsch** - Research Associate, WIP

**Institution:**
Technical University of Berlin  
Faculty VII (School of Economics and Management)  
Workgroup for Infrastructure Policy (WIP)  
Straße des 17. Juni 135, 10623 Berlin, Germany

---

*This repository represents academic work conducted at TU Berlin as part of the Operations Research seminar series, examining the intersection of transportation electrification and energy system optimization.*## Figures

### Network Topology
![Network Model](./Graphics/map.jpg)

### Technology Dispatch
**Baseline**
![Baseline Dispatch](./Graphics/production_by_technology.png)

**2025**
![Dispatch 2025](./Graphics/production_by_technology2025.png)

**2035**
![Dispatch 2035](./Graphics/production_by_technology2035.png)

### Storage & V2G Dispatch
**2025**
![Storage Dispatch 2025](./Graphics/StorageDispatch2025.png)

**2035**
![Storage Dispatch 2035](./Graphics/StorageDispatch2035.png)

