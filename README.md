## China Population Modelling Project  
*A Mathematical Exploration of Logistic Growth, Stability, and Numerical Simulation*

---

### Overview

China’s demographic contraction continued for a fourth straight year, according to January 2026 data from the National Bureau of Statistics. The total population fell by 3.39 million to 1.40489 billion, driven largely by a significant drop in annual births—from 9.54 million in 2024 to just 7.92 million in 2025.

These developments raise important mathematical questions:

- Can classical population models explain long-term demographic trends?
- Is logistic growth still an appropriate framework?
- What happens when a system approaches equilibrium?
- How reliable are numerical approximations of nonlinear models?

This study explores these questions through a structured mathematical modelling study of China's population data.

---

### Objectives

1. Fit a logistic growth model to historical population data (1950–2023).
2. Estimate model parameters using nonlinear regression.
3. Perform equilibrium and stability analysis.
4. Implement numerical approximations of the differential equation.
5. Compare numerical and analytical solutions.
6. Analyze discretisation error and numerical stability.

---

### Data

- CSV file containing annual population data (1950–2023).
- Population measured in billions.
- Data sourced from United Nations Data.

---

### Mathematical Model

We model population using the logistic differential equation:

$$\frac{dP}{dt} = rP\left(1 - \frac{P}{K}\right)$$

Where:

- $P$ = population
- $r$ = intrinsic growth rate  
- $K$ = carrying capacity  
- $A$ = integration constant  

Closed-form solution:

$$P(t) = \frac{K}{1 + Ae^{-rt}}\$$

---

### Estimated Parameters

Using nonlinear least squares regression:

- **Estimated K** ≈ 1.5988  
- **Estimated r** ≈ 0.0412  
- **Estimated A** ≈ 2.1548  

These parameters describe the long-term equilibrium level and growth dynamics implied by historical data.

---

### Project Structure
cn-population-modelling/

│

├── data/

│   └── china_pop_1950_2023_UN.csv

│

├── notebooks/

│   ├── 01_model_fitting.ipynb

│   ├── 02_equilibrium_and_stability_analysis.ipynb

│   └── 03_numerical_simulation.ipynb

│

├── README.md

└── requirements.txt

---

### Notebook Descriptions

#### Notebook 01 – Model Fitting

- Exploratory data analysis  
- Logistic model formulation  
- Nonlinear parameter estimation  
- Residual analysis  
- Goodness-of-fit discussion  
---

#### Notebook 02 – Equilibrium & Stability Analysis

- Identification of equilibrium points:
  - \( P = 0 \)
  - \( P = K \)
- Linearisation around equilibria  
- Stability classification  
- Interpretation in demographic context  

---

#### Notebook 03 – Numerical Simulation

- Euler method discretisation  
- Comparison with exact solution  
- Absolute error analysis  
- Step-size sensitivity  
- Numerical stability observations  

---

### Key Insights

- The logistic model fits mid-century growth reasonably well but struggles with recent structural decline.
- The carrying capacity parameter suggests a theoretical upper bound not currently reached.
- Stability analysis confirms that \( P = K \) is asymptotically stable under positive growth.
- Numerical simulations confirm first-order convergence of Euler’s method.
- Large time steps introduce discretisation instability.

---

### Limitations

- The logistic model assumes symmetric growth dynamics.
- It does not incorporate:
  - Policy shifts  
  - Age structure  
  - Migration  
  - Economic shocks  
- Declining birth rates suggest that future modelling may require modified or time-varying growth parameters.

---

### Possible Extensions

- Time-dependent growth rate \( r(t) \)  
- Piecewise logistic models  
- Leslie matrix age-structured modelling  
- Runge–Kutta numerical schemes  
- Bayesian parameter estimation  
- Model comparison (exponential vs logistic vs Gompertz)