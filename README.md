# Fitting Procedure of a Concave Price Impact Model with multi timescale decay

This repository contains a Jupyter Notebook that fits a **concave exponential impact decay model** with three time scales to a dataset of meta-orders. The goal is to study **nonlinear and transient price impact** in statistical arbitrage trading, accounting for empirical observations.

## Abstract
We study statistical arbitrage problems considering the nonlinear and transient price impact of metaorders. We derive simple explicit trading rules for general **nonparametric alpha and liquidity signals** and explore **extensions to multiple impact decay timescales**. Using a proprietary dataset of CFM metaorders, we **calibrate the impact model** by fitting the **concavity, decay parameters, and impact levels**, analyzing their effects on optimal execution.

## Repository Structure
- **`OR-ConcaveImpactEmpiric-R1.ipynb`**: The Jupyter Notebook for fitting the price impact model.
- **`meta_order_simdata-1.csv`**: The dataset containing simulated meta-orders.

## Dataset Description
The dataset consists of **meta-orders** and their corresponding impact parameters. The key columns include:

| Column          | Description |
|----------------|------------|
| `Mid_start`    | Midprice at the start of the meta-order |
| `Mid_end`      | Midprice at the end of the meta-order |
| `volatility_pts` | Price volatility during the meta-order (basis points) |
| `Q`           | Normalized meta-order volume relative to daily volume |
| `T`           | Duration of the meta-order (minutes) |
| `time`        | Timestamp (minutes) |
| `Product`     | Identifier of the futures contract |

## Model Fitting Procedure
- **Impact Function**: The model fits a **power-law impact function** with two or three decay timescales.
- **Two-Timescale Model (`n=2, c=0.5`)**:
  - Fits impact to two characteristic timescales and optimizes for best R².
- **Three-Timescale Model (`n=3, c=0.5`)**:
  - Extends the model to three impact decay scales for a more flexible fit.
- **Concavity Adjustment**:
  - Additional tuning of the concavity parameter for the two best-fitted timescales.

## Usage
1. Install dependencies:
   ```bash
   pip install -r requirements.txt
