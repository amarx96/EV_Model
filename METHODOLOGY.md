# Methodology

## Optimization Model Framework

### Objective Function
The model minimizes total system costs including:
- Capital expenditures (CAPEX) for generation, storage, and transmission
- Operational expenditures (OPEX) for maintenance and fuel
- Emission costs based on carbon pricing

```latex
\begin{equation}
\min_{g_{npt}, G_{np}, F_{nm}, \chi^{S}_{ns}, Z^{S}_{ns}, B^{S}_{ns}, B^{EV}_{nm}}
\quad
\sum_{n \in N} \sum_{p \in P} \sum_{t \in T} c^{g}_{npt} \cdot g_{npt}
+ \sum_{n \in N} \sum_{p \in P} c^{G}_{np} \cdot G_{np}
+ \sum_{n \in N} \sum_{m \in N} c^{F}_{nm} \cdot F_{nm}
+ \sum_{n \in N} \sum_{s \in S} \chi^{S}_{ns} \cdot c^{S,Capex,\chi}_{s}
+ \sum_{n \in N} \sum_{s \in S} Z^{S}_{ns} \cdot c^{S,Capex,Z}_{s}
+ \sum_{n \in N} \sum_{s \in S} B^{S}_{ns} \cdot c^{S,Capex,B}_{s}
+ c^{EV,Capex} \sum_{n \in N} \sum_{m \in N} \frac{B^{EV}_{nm}}{cap^{EV,B}} \tau_{nm}
\end{equation}

### Constraints

#### Energy Balance
- Supply-demand balance for each region and time period
- Grid capacity constraints for inter-regional power flows
- Storage operation constraints (charging/discharging limits)

\begin{equation}
\sum_{p \in P} g_{npt}
+ \sum_{m \in N} f_{mnt}
+ \sum_{m \in N} V^{EV}_{nm} \omega^{V}_{mnt} z^{EV}_{mnt}
+ \sum_{s \in S} z^{S}_{nst}
=
e_{nt} + \zeta_{nt}
+ \sum_{m \in N} f_{nmt}
+ \sum_{m \in N} V^{EV}_{nm} \omega^{V}_{nmt} x^{EV}_{nmt}
+ \sum_{s \in S} x^{S}_{nst}
\end{equation}

#### Technology Constraints
- Maximum installable capacity per technology and region
- Ramping constraints for conventional generation
- Efficiency losses in storage and transmission

\begin{equation}
g_{npt} = \omega^{RES}_{npt} G_{np}
\quad \forall p \in P^{RES}
\end{equation}

\begin{equation}
0 \le G_{np} \le cap^{G}_{np}
\quad \forall p \in P^{RES}
\end{equation}

\begin{equation}
0 \le g_{npt} \le G_{np}
\quad \forall p \in P^{F}
\end{equation}

\begin{equation}
0 \le f_{nmt} \le F_{nm} A_{nm}
\end{equation}

#### EV Integration Constraints
- Charging demand based on commuting patterns
- Battery capacity and charging rate limitations
- Vehicle-to-grid availability constraints

### Temporal Resolution
- Hourly optimization over representative days
- Seasonal variations captured through summer/winter scenarios
- Multi-year investment planning with technology learning curves

### Spatial Resolution
- German NUTS-2 regions as spatial units
- Grid topology based on existing transmission infrastructure
- EV commuting flows between metropolitan and rural areas

## Data Processing Pipeline

1. **Load Profile Generation**: Hourly electricity demand profiles
2. **Renewable Resource Assessment**: Wind and solar availability factors
3. **EV Pattern Analysis**: Commuting data processing for charging demand
4. **Technology Parameterization**: Cost and performance data compilation
5. **Scenario Definition**: Future technology and policy scenarios

## Solution Approach

The model is formulated as a mixed-integer linear program (MILP) and solved using commercial solvers. The dashboard provides real-time visualization of results through interactive plots and geographic maps.
