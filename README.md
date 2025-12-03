# Reservoir Optimization Replication

**Author:** Catherine Dansuah Grant  
**Course:** AREC 615 - Optimization Methods for Applied Economics

## Overview

This project replicates the reservoir optimization model by Chen et al. (2018) and extends it with drought policy constraints.

## Requirements

- R (version 4.0+)
- lpSolve package
```r
install.packages("lpSolve")
```

## How to Run

Open `replication.Rmd` in RStudio and click **Knit**, or run:
```r
rmarkdown::render("replication.Rmd")
```

## Code Walkthrough

### Part 1: Replication

1. **Set parameters** - Define storage states (5), inflow states (3), and time periods (4 quarters)
2. **Generate synthetic inflows** - Create 10 years of quarterly inflow data with seasonal patterns
3. **Discretize inflows** - Convert continuous inflows into 3 discrete states per quarter
4. **Estimate Markov transitions** - Calculate probability of moving between inflow states
5. **Compute power generation (G)** - Calculate electricity output for each state combination
6. **Build constraints** - Set up normalization, reliability, and vulnerability constraints
7. **Solve optimization** - Use lpSolve to maximize expected generation
8. **Compare results** - Check against Chen et al. (2018) values

### Part 2: Drought Extension

1. **Analyze baseline Q3 releases** - Find maximum summer water release
2. **Set drought limits** - Define moderate (90%), severe (80%), and extreme (70%) caps
3. **Add drought constraints** - Restrict Q3 releases to policy limits
4. **Solve each scenario** - Run optimization under each policy
5. **Compare costs** - Calculate generation losses and economic costs

## Files

| File | Description |
|------|-------------|
| `replication.Rmd` | Main analysis code |
| `synthetic_inflows.csv` | Simulated inflow data |
| `final_project_Catherine.pdf` | Full written report |

## Reference

Chen, C., Kang, C., & Wang, J. (2018). Stochastic linear programming for reservoir operation with constraints on reliability and vulnerability. *Water*, 10(2), 175.
