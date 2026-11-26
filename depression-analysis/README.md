# Depression scores and demographic data

Explore depression scores and demographic variables from **Depresjon**, predict follow-up MADRS scores from baseline scores, and examine affective-type classification from education.

## Files

- [depression_analysis.ipynb](depression_analysis.ipynb): exploratory plots, linear regression and logistic regression.
- [scores.csv](scores.csv): the unmodified official table, containing **55 participants and 12 columns**. Its rows and values were compared with the coursework copy and match exactly.

The sensor time-series folders are not needed by this notebook.

## Source and licence

Garcia-Ceja, E., Riegler, M., Jakobsen, P., Tørresen, J., Nordgreen, T., Oedegaard, K. J., and Fasmer, O. B. (2018). *Depresjon: A Motor Activity Database of Depression Episodes in Unipolar and Bipolar Patients*. MMSys '18. [Paper DOI](https://doi.org/10.1145/3204949.3208125).

Dataset: [Zenodo record 1219550](https://doi.org/10.5281/zenodo.1219550), published by the dataset authors. Licensed **[Creative Commons Attribution–NonCommercial 4.0](https://creativecommons.org/licenses/by-nc/4.0/)**. Retain attribution and observe the noncommercial condition when reusing the data. No changes were made to `scores.csv`.

The official archive has MD5 `6c96ed5ec92ef551b2db1c7f1276809d`. The downloaded archive was checked against the publisher's checksum before comparison.

## Reading the variables

The [official project page](https://datasets.simula.no/depresjon/) documents the variables. `madrs1` and `madrs2` are scores at the start and end of measurement. `afftype` identifies bipolar II (1), unipolar depression (2) or bipolar I (3); it is not a depressed-versus-healthy label. `age` and `edu` are grouped categories. `number` is a pseudonymous participant identifier. The remaining columns describe recording duration, gender, melancholia, inpatient status, marriage and work status.

## Method and limits

The linear model predicts `madrs2` from `madrs1` using observed outcomes and a fixed 80/20 split. Predictor imputation is fitted on the training set only. The logistic model predicts `afftype` from education using the original 70/30 split and category encoding.

The small samples, single splits and education-only classifier do not establish clinical usefulness. Education encoding is retained from the original coursework and should not be interpreted as a validated numerical scale. Missing outcomes are not invented for controls or used as observed values in the plots.

## Validation and preparation

The CSV was matched to this notebook and all Python cells passed syntax checks. A full end-to-end execution of this prepared copy has not been verified.

Missing imports were added, observed outcomes are retained for exploration and regression, and the subject plots are described as cross-subject comparisons rather than time series. Undefined classification metrics are reported as zero. Saved outputs are cleared.
