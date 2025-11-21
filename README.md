# Hybrid Derivative Pricing: Heston-Hull-White Model

This project contains a professional Monte Carlo pricing engine for a hybrid equity-rate derivative using the Heston-Hull-White model.

## Features

- **Heston Stochastic Volatility Model** for equity with Full Truncation discretization scheme
- **Hull-White One-Factor Model** for interest rates with closed-form bond pricing
- **Vectorized NumPy implementation** (no Python loops over paths)
- **Correlated Brownian motions** via Cholesky decomposition
- **Convergence analysis** with visualization
- **Distribution analysis** of key simulation outputs

## Requirements

```bash
pip install numpy matplotlib jupyter
```

## Usage

1. Open the Jupyter notebook:
```bash
jupyter notebook hybrid_derivative_pricing.ipynb
```

2. Run all cells to execute the pricing engine

## Model Parameters

Default parameters are set in the `ModelParameters` dataclass:
- Equity: S0=100, v0=0.04, κ=2.0, θ=0.04, ξ=0.3
- Rates: r0=0.03, a=0.05, σ_r=0.01
- Correlations: ρ(S,v)=-0.7, ρ(S,r)=0.3, ρ(v,r)=0.0
- Product: T=1.0, Δ=0.25, k=1.0, k'=1.0, N=1.0
- Simulation: M=50,000 paths, 12 time steps (monthly)

## Output

The notebook provides:
- Price and standard error
- 95% confidence interval
- Convergence analysis plots
- Distribution plots for equity, rates, and payoffs
- Model validation (correlation matrix verification)

