# Finnish energy consumption

Compare ordinary linear regression with Lasso regression to predict total energy consumption in Finland.

## Notebook

[`energy_regression.ipynb`](energy_regression.ipynb) loads the data, fits both models and compares predictions using mean absolute error. The original split uses the first 11 rows for training and the following 3 rows for testing; Lasso uses `alpha=0.001`.

## Data

Place the original `energy_data.csv` beside the notebook. It must contain `Year`, `Energy Consumption Total(TJ)` and the numeric predictor columns used in the original assignment. The target is total consumption; `Year` and the target are excluded from predictors. The source dataset and its attribution were not present in the supplied notebook, so they must be confirmed before redistributing data.

## Interpretation

The test set is very small. The split is based on row order and is only chronological if the CSV is ordered by year. Results from this experiment do not establish reliable future forecasting. Predictor scaling, time-aware validation and the possibility that predictors are components of total consumption should be examined before drawing stronger conclusions.

## Preparation notes

The original model choices and split are retained. Score labels were corrected from “covariance” to training R-squared, and both models now report plain MAE. The original Lasso evaluation added an extra coefficient penalty to MAE; that term was removed to make prediction errors comparable. Outputs were cleared. The prepared notebook has not been rerun because the CSV was not supplied.
