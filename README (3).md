# INR–USD Exchange Rate Prediction

A simple data analysis and machine learning script that visualizes historical INR–USD exchange rate data and predicts the closing rate using a Decision Tree Regressor.

## Overview

This project walks through a basic end-to-end workflow for time-series-style financial data:

1. Load historical forex data from a CSV file.
2. Visualize the closing exchange rate over time.
3. Explore correlations between numeric features with a heatmap.
4. Train a `DecisionTreeRegressor` to predict the closing rate from the day's `Open`, `High`, and `Low` values.
5. Output predictions on a held-out test set.

## Features

- Quick visual inspection of the dataset (`.head()`, line plot of closing rate)
- Correlation heatmap across all numeric columns using Seaborn
- Train/test split (80/20) with `scikit-learn`
- Decision tree regression model trained on `Open`, `High`, `Low` to predict `Close`
- Predicted values collected into a clean output DataFrame

## Requirements

- Python 3.8+
- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn

## Installation

```bash
pip install numpy pandas matplotlib seaborn scikit-learn
```

## Dataset

The script expects a CSV file with at least the following columns:

- `Open`
- `High`
- `Low`
- `Close`

By default, the script reads from:

```
/content/forex_data_2020-2025.csv
```

This path is set up for a Google Colab environment (`/content/...`). If running locally, update this path to point to your own copy of the dataset, for example:

```python
data = pd.read_csv("forex_data_2020-2025.csv")
```

## Usage

```bash
python main.py
```

Running the script will:

1. Print the first few rows of the dataset.
2. Display a line chart of the INR–USD closing rate over time.
3. Print and plot a correlation heatmap of all numeric columns.
4. Split the data into training and test sets.
5. Train a Decision Tree Regressor on `Open`, `High`, `Low` to predict `Close`.
6. Print the first few predicted closing rates.

## Project Structure

```
.
├── main.py   # Data loading, visualization, and Decision Tree regression
└── README.md
```

## Notes & Possible Improvements

- The model currently uses only `Open`, `High`, and `Low` as features — adding lagged values, moving averages, or volume could improve predictive power.
- No evaluation metrics (e.g., MAE, RMSE, R²) are currently printed — consider adding these to assess model performance.
- A single Decision Tree can overfit easily; trying `RandomForestRegressor` or gradient boosting models (e.g., XGBoost) may yield more robust results.
- Consider scaling/normalizing features for models sensitive to feature magnitude.
- A fixed `random_state=42` is used for reproducibility of the train/test split.

## License

MIT — feel free to use, modify, and share.
