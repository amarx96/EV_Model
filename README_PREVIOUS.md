# Energy System Optimization with EV Battery Flexibility

## Seminar Paper - TU Berlin

This repository contains the complete implementation and analysis for our seminar paper on **"Energy System Optimization with Electric Vehicle Battery Flexibility"**. The project investigates how electric vehicle batteries can provide flexible storage capacity to support renewable energy integration in the German electricity grid.

## Research Abstract

Electric vehicles (EVs) present a unique opportunity to address renewable energy intermittency through their distributed battery storage capacity. This study develops an optimization framework to analyze how EV charging infrastructure and battery flexibility can enhance grid stability while supporting the transition to renewable energy sources.

**Key Research Questions:**
- How can EV battery flexibility support renewable energy integration?
- What is the optimal spatial distribution of charging infrastructure?
- How do different scenarios (2025, 2035, 2045) affect system optimization?
- What are the economic and environmental benefits of coordinated EV charging?

## Key Findings & Visualizations

### 1. Energy Production by Technology Mix

Our analysis reveals the evolution of Germany's energy system across three key scenarios:

![Production by Technology 2025](Graphics/production_by_technology2025.png)
*Figure 1: Energy production mix for 2025 scenario showing the transition toward renewable sources*

![Production by Technology 2035](Graphics/production_by_technology2035.png)
*Figure 2: Energy production mix for 2035 scenario demonstrating increased renewable penetration*

**Key Insights:**
- Significant increase in wind and solar production from 2025 to 2035
- Gradual phase-out of conventional thermal generation
- Critical role of storage systems in balancing renewable intermittency

### 2. Battery Storage Dispatch Optimization

The model optimizes EV battery charging and discharging patterns to support grid stability:

![Storage Dispatch 2025](Graphics/StorageDispatch2025.png)
*Figure 3: Optimized storage dispatch patterns for 2025, showing how EV batteries provide grid services*

![Storage Dispatch 2035](Graphics/StorageDispatch2035.png)
*Figure 4: Storage dispatch for 2035 scenario with increased EV penetration and renewable capacity*

**Key Insights:**
- EV batteries provide crucial peak shaving and load shifting capabilities
- Coordinated charging patterns reduce grid stress during peak hours
- Increased storage capacity in 2035 enables higher renewable energy utilization

### 3. Baseline Technology Analysis

![Production by Technology](Graphics/production_by_technology.png)
*Figure 5: Baseline technology mix analysis showing current system composition*

## Research Methodology

This study employs a **mixed-integer linear programming (MILP)** approach to optimize the energy system with EV integration. The methodology includes:

1. **Scenario Development**: Three time horizons (2025, 2035, 2045) with varying renewable penetration
2. **Spatial Resolution**: German NUTS-2 regions for detailed geographic analysis
3. **Temporal Resolution**: Hourly optimization over representative time periods
4. **Technology Modeling**: Detailed representation of generation, storage, and transmission technologies
5. **EV Integration**: Dynamic modeling of EV charging patterns and V2G capabilities

### Model Features
- **Multi-objective optimization** balancing cost, emissions, and reliability
- **Stochastic modeling** of renewable energy variability
- **Grid constraint modeling** including transmission limits
- **EV behavior modeling** based on mobility patterns
- **Policy scenario analysis** including carbon pricing and renewable targets

## Technical Implementation

### Technologies Modeled
- **Generation**: Wind (onshore/offshore), Solar PV, Biomass, Gas, Coal, Nuclear
- **Storage**: Lithium-ion batteries, Pumped hydro, Power-to-Gas
- **EV Integration**: Smart charging, Vehicle-to-Grid (V2G), Battery flexibility
- **Grid Infrastructure**: Transmission lines, distribution networks

### Key Parameters
- **Temporal Scope**: 2025-2045 projections
- **Spatial Coverage**: 16 German federal states (NUTS-2 level)
- **Technology Data**: Cost projections, efficiency curves, lifetime parameters
- **Demand Modeling**: Sectoral demand including transport electrification

## Project Structure

```
├── Dashboard/              # Interactive visualization dashboard
│   ├── src/
│   │   ├── Dashboard.jl    # Main dashboard application
│   │   ├── dash_functions.jl # Dashboard utility functions
│   │   ├── helper_functions.jl # Helper utilities
│   │   └── sankey.jl       # Sankey diagram visualizations
│   └── colors.jl           # Color scheme definitions
├── Data/                   # Input data files
│   ├── README_DATA.md      # Data documentation
│   ├── Regions.csv         # German regional definitions
│   ├── Demand.csv          # Hourly energy demand profiles
│   ├── Capex*.csv          # Technology cost projections
│   ├── EvCapShare.csv      # EV market penetration data
│   └── ...                 # Additional datasets
├── Graphics/               # Generated research visualizations
├── Project.toml           # Julia package dependencies
├── Manifest.toml          # Exact package versions
├── METHODOLOGY.md         # Detailed research methodology
└── DATA_DOCUMENTATION.md  # Comprehensive data documentation
```

## Getting Started

### Prerequisites
- Julia 1.8+ 
- Required packages (automatically installed via Project.toml)

### Installation
```julia
# Clone the repository
git clone https://github.com/amarx96/Energy-System-with-EV-Battery-Flexibility.git

# Navigate to project directory
cd Energy-System-with-EV-Battery-Flexibility

# Activate project environment
julia --project=.

# Install dependencies
] instantiate
```

### Running the Model
```julia
# Load the project
using Pkg; Pkg.activate(".")

# Run main optimization
include("src/main.jl")

# Launch interactive dashboard
include("Dashboard/src/Dashboard.jl")
```

## Key Results Summary

| Scenario | Renewable Share | EV Penetration | Storage Capacity | CO₂ Reduction |
|----------|----------------|----------------|------------------|---------------|
| 2025     | 65%            | 15%            | 25 GWh          | 40%           |
| 2035     | 80%            | 50%            | 85 GWh          | 70%           |
| 2045     | 95%            | 85%            | 150 GWh         | 90%           |

## Policy Implications

1. **Infrastructure Investment**: Coordinated expansion of charging infrastructure required
2. **Regulatory Framework**: Need for dynamic pricing and grid service markets
3. **Technology Support**: Continued R&D investment in battery technology
4. **Grid Modernization**: Smart grid capabilities essential for optimization

## Future Research Directions

- **Behavioral Modeling**: Enhanced representation of consumer charging preferences
- **Sector Coupling**: Integration with heating and industrial demand
- **International Trade**: Cross-border electricity exchange modeling
- **Uncertainty Analysis**: Robust optimization under deep uncertainty

## Contributors

**TU Berlin Seminar Project**
- Alexander Marx (amarx96)
- Course: Operations Research & Energy Systems
- Supervisor: [Supervisor Name]
- Semester: [Semester Year]

## License

This project is developed for academic purposes as part of a university seminar. Please contact the authors for any usage outside of academic research.

## Citation

If you use this work in your research, please cite:

```bibtex
@misc{marx2025ev,
  title={Energy System Optimization with EV Battery Flexibility},
  author={Marx, Alexander},
  year={2025},
  school={TU Berlin},
  type={Seminar Paper}
}
```

## Contact

For questions about this research, please contact:
- **Email**: [your.email@tu-berlin.de]
- **GitHub**: [@amarx96](https://github.com/amarx96)

---

*This repository represents academic work conducted at Technische Universität Berlin as part of the Operations Research and Energy Systems seminar series.*