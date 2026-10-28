
# Production Profit Optimizer

**A Mathematical Optimization and Risk Analysis Project**

Final project for the **Math Concepts for Developers** course at SoftUni — AI and Machine Learning Program, 2026.

## Project Overview

Production Profit Optimizer is a Python-based decision-support tool that helps businesses determine a profitable production quantity and selling price while considering production costs, budget constraints, customer demand, and uncertainty.

The project combines mathematical modeling, deterministic and stochastic optimization, Monte Carlo simulation, and sensitivity analysis.

The complete implementation and mathematical explanations are available in the Jupyter Notebook:

**`production_profit_optimizer.ipynb`**

## Main Features

- **Deterministic Optimization:** Finds the selling price and production quantity that maximize profit under predicted demand.
- **Stochastic Optimization:** Uses simulated demand scenarios to maximize estimated average profit.
- **Monte Carlo Risk Analysis:** Estimates average profit, probability of financial loss, and profit variability.
- **Budget Sensitivity Analysis:** Examines how changes in the production budget affect maximum profit.
- **Interactive Interface:** Allows users to modify business parameters through `ipywidgets`.
- **Results Dashboard:** Presents optimization results and three supporting visualizations.
- **Input Validation:** Prevents invalid parameters and excessively large simulation workloads.

## Mathematical Model

The project uses a linear demand function:

\[
D(p) = a + bp
\]

where \(p\) is the selling price and \(a\) and \(b\) are estimated from two price-demand observations.

Total production cost is modeled as:

\[
C(q) = F + cq
\]

Profit is calculated as:

\[
P(q,p) = p \cdot \min(q,D(p)) - C(q)
\]

where:

- \(q\) is the production quantity;
- \(F\) is the fixed production cost;
- \(c\) is the variable cost per unit;
- \(D(p)\) is the predicted customer demand.

The model accounts for budget restrictions and a minimum order quantity.

For stochastic analysis, demand is simulated using a normal distribution with non-negative integer outcomes.

More detailed mathematical explanations, assumptions, and validation are provided in the Notebook.

## Technologies

- Python 3.12.4
- NumPy 2.5.4
- Matplotlib 3.11.2
- ipywidgets 8.1.9
- IPython 9.17.1
- ipykernel 7.4.0
- Jupyter Notebook
- Visual Studio Code

The package versions above were used during development and testing on Windows.

## Installation and Setup

### 1. Prerequisites

Install the following software:

- Python 3.12
- Git
- Visual Studio Code
- VS Code Python extension
- VS Code Jupyter extension

### 2. Clone the Repository

Open a terminal and run:

```powershell
git clone https://github.com/MariaStoitseva/production-profit-optimizer.git
cd production-profit-optimizer
```

Alternatively, download the repository as a ZIP archive from GitHub and extract it.

### 3. Create a Virtual Environment

From the project directory, run:

```powershell
python -m venv .venv
```

### 4. Install Dependencies

A virtual environment does not need to be activated when using its Python executable directly.

In Windows PowerShell, run:

```powershell
.\.venv\Scripts\python.exe -m pip install -r requirements.txt
```

This installs the Python packages specified in `requirements.txt`.

### 5. Open the Notebook in VS Code

Open the project folder in Visual Studio Code.

Then open:

`production_profit_optimizer.ipynb`

In the upper-right corner of the Notebook, select the Python kernel associated with the project's `.venv` environment.

### 6. Run the Notebook

Click **Run All** to execute the Notebook from top to bottom.

After execution finishes, find the interactive input form and click **Run Optimization** to generate the results dashboard and visualizations.

The optimization may take some time, depending on the number of simulations and the selected search parameters.

## Using the Interactive Optimizer

The interface allows users to configure:

**Production Parameters**
- Production budget
- Fixed production cost
- Variable production cost per unit
- Minimum order quantity

**Demand Parameters**
- Two selling prices
- Expected demand at each price

**Simulation Parameters**
- Demand uncertainty
- Number of Monte Carlo simulations
- Price search step

After selecting the parameters, click **Run Optimization**.

The application displays:

1. Deterministic optimization results.
2. Stochastic optimization results.
3. Monte Carlo risk metrics.
4. Deterministic profit versus selling price.
5. Monte Carlo profit distribution.
6. Maximum profit versus production budget.

## Example Results

Using the default parameters, the deterministic model identifies:

| Metric | Result |
|---|---:|
| Optimal selling price | 4.25 EUR |
| Optimal production quantity | 1,375 units |
| Maximum deterministic profit | 3,281.25 EUR |

Stochastic results depend on randomly generated demand scenarios and may differ between executions.

## Testing and Validation

The project includes tests and mathematical checks covering:

- Production cost and profit calculations.
- Budget constraints and feasible production quantities.
- Numerical and analytical optimization consistency.
- Deterministic and stochastic consistency under zero uncertainty.
- Monte Carlo simulations and risk metrics.
- Input validation and boundary conditions.

The Notebook has also been executed from a restarted Jupyter kernel, and the interactive interface has been tested in VS Code.

## Limitations

The model assumes:

- A linear relationship between price and demand.
- Constant variable production costs.
- A single product.
- Normally distributed demand uncertainty.
- A finite range of candidate selling prices.

These assumptions simplify the optimization problem and may not fully represent real-world business conditions.

## Project Structure

```text
production-profit-optimizer/
├── production_profit_optimizer.ipynb
├── requirements.txt
├── README.md
└── .gitignore
```

The `.venv` directory is created locally during setup and should not be committed to Git.

## Author

Maria Stoitseva

SoftUni — AI and Machine Learning, 2026
