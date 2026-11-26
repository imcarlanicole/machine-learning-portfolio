# Machine learning and biomedical data portfolio

**Carla-Nicole Oatu** · Biomedical Engineering master's student at Aalto University

Academic projects in regression, biomedical data analysis and menstrual health. Each project folder contains notebooks, the analysis objective, data requirements and limitations.

| Project | Question | Methods |
| --- | --- | --- |
| [Finnish energy consumption](finland-energy/) | How do linear and Lasso regression compare for predicting total energy consumption? | Linear regression, Lasso, MAE, R-squared |
| [Menstrual health](menstrual-health/) | How do sleep, hormones and wrist temperature vary across cycle phases, and how well can phase be classified? | Data cleaning, visualization, Kruskal-Wallis, Spearman correlation, decision trees, random forests |
| [Depression data analysis](depression-analysis/) | How are depression scores related, and what patterns appear in demographic data? | Exploratory analysis, linear regression, logistic regression |

## Tools

Python, pandas, NumPy, Matplotlib, seaborn, SciPy, scikit-learn and Jupyter.

## Run locally

1. Install Python and create a virtual environment.
2. From this repository, install dependencies with `python -m pip install -r requirements.txt`.
3. Obtain the datasets described in each project README and place the required files beside the corresponding notebook.
4. Launch `jupyter lab`, open a notebook and run its cells in order.

## Data and reproducibility

Source data and saved notebook outputs are not included. The notebooks have been prepared for sharing, checked for Python syntax and documented, but the prepared copies have not been rerun against the original datasets. Numerical results should be regenerated before they are cited. Project READMEs record the small corrections made during preparation and the limits of the original experiments.
