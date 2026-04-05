# Allocation Return Direction Prediction

We aim to predict the **sign of next-day returns** for a set of asset allocations using their recent history of returns and signed volumes.

- We start from a simple baseline: **short-term momentum**, modeled with:
  - logistic regression (strongly regularized)  
  - a shallow penalized decision tree  

- We work in a **pooled cross-sectional setting**, treating each allocation as a strategy  

- Rather than relying on raw lags, we progressively build **profile-based features**:
  - return structure (trend, stability, monotonicity)  
  - flow dynamics (signed volume persistence, imbalance, exhaustion)  
  - market conditions (volatility, turnover, group structure)  
  - interactions between flow and returns  

- We combine the objective of pure prediction with an objective of **selection**:
  - identify when an allocation is **predictable**  
  - focus on **cross-sectional ranking within each day**  

- Performance is evaluated through:
  - direction prediction  
  - return and return change (value and sign)  
  - ranking quality across allocations  
  - conditional analysis (volatility, turnover, group)  

- We explicitly account for **regime dependence**, as predictability varies with:
  - flow persistence vs exhaustion  
  - market volatility and dispersion  

**Goal:**  
not just predict returns, but detect when a strategy is in a **predictable state and worth trading**
