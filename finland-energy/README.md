# Finnish energy consumption

Compare linear regression and Lasso regression on a small annual dataset from a machine-learning course project.

## Files and data

- [energy_regression.ipynb](energy_regression.ipynb): data loading, model fitting and error comparison.
- [energy_data.csv](energy_data.csv): the original 14-row table recovered from the coursework workspace, covering **2008–2021**. Values have not been changed.

The predictors are `Families`, `GDP Per Capita`, `Unemployment rate` and `Number of tourists`. The target column is labelled `Energy Consumption Total(TJ)`. `Year` is used to describe the split and is excluded from the model inputs.

**Provenance:** the table came from the original Jupyter workspace (`notebooks/energy_data.csv`). Its original statistical sources, GDP currency basis and the exact scope of the energy measure have not been recovered. It should not be presented as a verified official series for Finland's total national energy use. No third-party open-data licence is asserted for this coursework table.

## Method

The original chronological split is retained: **2008–2018 for training (11 rows)** and **2019–2021 for testing (3 rows)**. Both models use the same four predictors; Lasso uses `alpha=0.001`. The notebook reports training R-squared and mean absolute error for training and test predictions.

## Interpretation

Three test observations cannot establish robust forecasting performance. Predictors are unscaled, so Lasso's penalty depends on the variable units. The notebook illustrates a modelling workflow; stronger conclusions require verified source definitions, scaling and time-aware validation with substantially more observations.

## Validation and preparation

The CSV was matched to this notebook and all Python cells passed syntax checks. A full end-to-end execution of this prepared copy has not been verified.

The original model choices, data values and split are retained. Mislabelled “covariance” scores were renamed training R-squared. The Lasso prediction error now uses plain MAE without adding a coefficient penalty. Saved outputs are cleared so rerunning the notebook generates the results.
