# Depression scores and demographic data

Explore MADRS scores and demographic variables, fit linear regression to predict `madrs2` from `madrs1`, and use logistic regression to explore `afftype` classification from education.

## Notebook

[`depression_analysis.ipynb`](depression_analysis.ipynb) includes missing-value handling, score distributions, demographic comparisons, regression and classification.

## Data

Place the original `scores.csv` beside the notebook. Referenced columns are `number`, `madrs1`, `madrs2`, `afftype`, `edu`, `days`, `age`, `work`, `marriage` and `melanch`. The supplied notebook did not identify the data source or provide a data dictionary. Verify the source, coding and access terms before interpreting or redistributing the data.

## Interpretation

This is an exploratory academic exercise. A single small train/test split and a model using education alone do not establish clinical usefulness. The original education encoding is retained; its ordinal interpretation should be checked against the data dictionary. Complete-case filtering can introduce selection bias. No clinical-performance claim is made.

## Preparation notes

Missing imports were added. Linear regression now uses observed targets and fits predictor imputation on the training set only. The prediction comment was corrected to MADRS2, and the subject plot is described as a comparison across subjects rather than a time series. Undefined classification metrics are reported as zero. Outputs were cleared. The cleaned version has not been rerun because the CSV was not supplied.
