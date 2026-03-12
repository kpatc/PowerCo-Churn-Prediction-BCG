# PowerCo Churn Prediction – BCG X Simulation

## Project Overview
This repository documents a data science case simulation for BCG X, focusing on customer churn at PowerCo, an energy provider. The goal is to identify the drivers of churn—especially price sensitivity—and build predictive models to inform business strategy.

## Business Problem
PowerCo suspects that price sensitivity is causing customers to switch to lower-cost providers. However, churn may be influenced by multiple factors, including contract terms, service quality, and customer origin. The project aims to validate or disprove the price hypothesis and uncover actionable insights.

## Workflow & Tasks

### Task 2: Exploratory Data Analysis (EDA)
- Data understanding: Analyzed customer and pricing datasets.
- Distribution analysis: Visualized categorical and numerical variables.
- Bivariate analysis: Explored relationships between churn and key features (channel, contract, margins, gas, etc.).
- Insights: Identified initial patterns and potential churn drivers.

### Task 3: Feature Engineering & Modeling (Next Steps)
- Feature creation: Engineer new variables to capture price changes, contract dynamics, and customer behavior.
- Model building: Train and evaluate classification models (e.g., Random Forest, XGBoost) to predict churn.
- Interpretation: Quantify feature importance and simulate business interventions.

## Data Sources
- `client_data.csv`: Customer profiles, consumption, contract info, churn labels.
- `price_data.csv`: Monthly pricing history (variable and fixed rates).

## Technologies
- Python (Pandas, NumPy, Matplotlib, Seaborn, Scikit-learn)
- Jupyter Notebook

## Structure
- `data/`: Raw datasets
- `eda/`: Notebooks for EDA and visualizations
- `requirements.txt`: Python dependencies

## Getting Started
1. Clone the repository.
2. Install dependencies:  
   `pip install -r requirements.txt`
3. Run notebooks in `eda/` for EDA and visualizations.

## Author
BCG X Data Scientist Simulation  
[Your Name]

---

**Next Steps:**  
Move to Task 3 – Feature Engineering and Modeling.  
Stay tuned for updates and new notebooks!
