# Bayesian Analysis of Mushroom Preservation

**Authors:** Alessandro Mecchia & Sergio Fernandez Diz

## Project Overview

This project implements a Bayesian analysis to model the impact of **storage temperature** on the **spoilage rate** of harvested oyster mushrooms using Bayesian logistic regression.

## Problem Description

The main objective is to estimate the parameters (α, β) of a probabilistic model that links storage temperature to the probability that a mushroom spoils after 5 days of storage.

### Mathematical Model

The relationship between temperature and spoilage probability is defined by the **logistic function**:

$$p_i = \text{sigm}(\alpha + \beta x_i) = \frac{1}{1 + e^{-(\alpha + \beta x_i)}}$$

Where:
- **α (intercept)**: Baseline log-odds of spoilage at 0°C
- **β (slope)**: Rate of change in spoilage risk with temperature
- **x_i**: Storage temperature in °C
- **p_i**: Probability of spoilage

### Probabilistic Model Structure

#### Likelihood
The number of spoiled mushrooms follows a **Binomial distribution**:

$$y_i | \alpha, \beta \sim \text{Bin}(n_i, p_i)$$

#### Prior Distributions
The model parameters have **Gaussian priors**:
- **α ~ N(0, 2²)**: Intercept parameter
- **β ~ N(0, 1²)**: Slope parameter

## Experimental Data

The analysis uses data from an experiment conducted across 4 storage temperature levels:

| Temperature (°C) | Total Mushrooms | Spoiled Mushrooms |
|:----------------:|:---------------:|:-----------------:|
| 2                | 30              | 2                 |
| 8                | 25              | 4                 |
| 15               | 20              | 5                 |
| 25               | 30              | 20                |

## Methods Implemented

The project explores multiple Bayesian inference approaches:

1. **Full Probabilistic Model Derivation**
   - Likelihood function formulation
   - Prior specification
   - Posterior distribution (unnormalized)

2. **MAP Estimation** (Maximum A Posteriori)
   - Numerical optimization for point estimates

3. **Grid Approximation**
   - Discrete approximation of posterior distribution

4. **MCMC Sampling**
   - Metropolis algorithm implementation
   - Convergence diagnostics
   - Posterior analysis

## Project Structure

```
.
├── project.ipynb          # Main Jupyter notebook with analysis
├── project.html           # HTML export of the notebook
├── requirements.txt       # Python dependencies
├── Pipfile               # Pipenv configuration
└── README.md             # This file
```

## Requirements

### Python Version
- Python 3.8+

### Main Dependencies
- `numpy` - Numerical computing
- `scipy` - Scientific computing and statistics
- `matplotlib` - Data visualization
- `seaborn` - Statistical data visualization
- `pandas` - Data manipulation
- `plotly` - Interactive visualizations

For a complete list of dependencies, see [requirements.txt](requirements.txt).

## Installation

### Option 1: Using pip

```bash
pip install -r requirements.txt
```

### Option 2: Using Pipenv

```bash
pipenv install
pipenv shell
```
## Usage

1. Clone or download this repository
2. Install the required dependencies
3. Open the Jupyter notebook:
   ```bash
   jupyter notebook project.ipynb
   ```
## Results

The analysis provides:
- Parameter estimates for α and β
- Posterior distributions with uncertainty quantification
- Predictive probabilities for new temperature values
- Comparison of different inference methods
- Convergence diagnostics for MCMC sampling

## License

This is an academic project for the Bayesian Data Analysis course at SUPSI.

## Contact

For questions or feedback, please contact the authors:
- Alessandro Mecchia
- Sergio Fernandez Diz
