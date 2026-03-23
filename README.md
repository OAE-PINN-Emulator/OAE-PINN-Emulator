# OAE-PINN-Emulator

Physics-Informed Neural Network (PINN) emulator for ocean tracer transport in the context of Ocean Alkalinity Enhancement (OAE).

## 🌍 Motivation

Ocean Alkalinity Enhancement (OAE) is a promising marine carbon dioxide removal (mCDR) strategy. However, resolving the transport and evolution of alkalinity in the ocean requires computationally expensive simulations.

This project explores whether Physics-Informed Neural Networks (PINNs) can act as fast, accurate emulators of tracer transport governed by advection–diffusion dynamics.

## 🧠 Core Idea

We model tracer evolution using the advection–diffusion equation:

```
∂C/∂t = D(∂²C/∂x² + ∂²C/∂y²) − u ∂C/∂x − v ∂C/∂y + S(x, y, t)
```

A neural network is trained to:
- Fit simulation data (Oceananigans output)
- Respect underlying physics via PDE-based loss terms

## 📊 Experiments

### 1. Single Realization
- Train PINN on one Oceananigans simulation
- Evaluate reconstruction ability

### 2. Multiple Realizations
- Train on multiple forcing conditions
- Test generalization

### 3. Physics Loss Analysis
- Compare with vs without physics constraints
- Study stability and long-term behavior

### 4. Single-step vs Multi-step Forecasting
- Evaluate rollout performance
- Analyze error accumulation


## 📁 Repository Structure

```
.
├── notebooks/
│   ├── 01_oceananigans_single_realization.ipynb
│   ├── 02_oceananigans_multiple_realizations.ipynb
│   ├── 03_physics_loss_analysis.ipynb
│   └── 04_single_step_vs_multi_step.ipynb
├── README.md
├── LICENSE
```

## ⚙️ Methods

- Ocean simulations: Oceananigans.jl  
- ML framework: PINNs (PyTorch)  
- Loss:
  - Data loss
  - Physics loss (PDE)
  - (Optional) mass conservation  

## 📈 Key Questions

- Can PINNs emulate tracer transport?
- Do physics constraints improve generalization?
- How does error evolve in multi-step forecasts?

## 🔬 Climate Relevance

OAE efficiency depends on ocean transport and CO₂ exchange. Models are essential but expensive. This work explores fast ML-based emulators for climate-relevant simulations.

## 🚀 Future Work

- Add mass conservation constraint  
- Generalize across forcings  
- Extend to biogeochemistry  
- Add uncertainty quantification  

## Author

Kavya Agarwal  
Yale University — Earth & Planetary Sciences  
