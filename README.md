# Allocation Return Direction Prediction

## Objective
The goal of this challenge is to predict the **direction of next-day returns** for a set of asset allocations using 20 lagged returns and signed volumes.

## Approach

- We start with a simple baseline based on **short-term momentum**, using:
  - logistic regression  
  - a heavily regularized decision tree  

- Models are trained in a **pooled cross-sectional setting** across all allocations  

- Performance is evaluated **conditionally** on:
  - volatility  
  - turnover  
  - a GROUP variable  

- We then progressively construct additional signals capturing:
  - strategy strength  
  - market conditions  
  - interactions with flow (signed volume)  

- Signals are evaluated based on their ability to predict:
  - next-day return  
  - the sign of next-day return  
  - the change in returns (and its sign)  

- We also evaluate performance in a **cross-sectional setting** by:
  - ranking allocations within each day  
  - combining this ranking with a prediction of **market breadth**  

## Goal
Build signals that improve prediction while understanding **when and where they are effective**.
