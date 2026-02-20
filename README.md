## Project Motivation

In many machine learning workflows, models are compared while the optimizer is treated as a default choice.

However, in real production systems:

- **Training cost** depends on convergence speed  
- **Stability** affects reliability  
- **Generalization** impacts deployment performance  

This project isolates the **optimization algorithm** and studies its direct influence on model behavior.

---

## Task

Design an experiment that compares optimizers **beyond accuracy**.

### Key Requirements
- Same model  
- Same dataset  
- Same initialization  
- Only the optimizer changes  
- Measure training dynamics instead of only final performance  

---

## Optimizers Evaluated

| Optimizer | Category | Description |
|--------|------|------|
| Vanilla Gradient Descent | Deterministic | Full-batch gradient updates |
| Momentum Gradient Descent | Accelerated | Uses velocity to speed up convergence |
| Stochastic Gradient Descent (SGD) | Mini-batch | Noisy but computationally efficient |
| SPSA | Gradient-free | Estimates gradient via perturbations |

---

## Evaluation Metrics

- Train / Validation / Test **Loss & Accuracy**
- **Gradient Norm Decay**
- **Runtime**
- Iterations to reach **95% loss improvement**

---

## Visualization

Learning dynamics are analyzed using:

- Loss vs Iteration
- Smoothed Loss Curves
- Accuracy Curves
- Gradient Norm Decay

---

## Key Insights

- **Momentum GD** converges the fastest  
- **SGD** is computationally most efficient  
- Accuracy alone is misleading → *lowest loss ≠ highest accuracy*  
- Gradient-free methods struggle when gradients are available  

---

## Experimental Results

| Optimizer | Test Accuracy | Test Loss | Behavior |
|--------|------|------|------|
| Vanilla GD | ~98.25% | Stable | Slow but reliable |
| Momentum GD | ~96.5% | Lowest | Fastest convergence |
| SGD | ~98.25% | Efficient | Fast runtime, noisy updates |
| SPSA | ~97.3% | High variance | Slow & unstable |

---

## Tech Stack

- Python  
- NumPy  
- Pandas  
- Matplotlib  

**All optimization algorithms are implemented manually (from scratch).**
