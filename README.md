# Machine learning and biomedical data portfolio

**Carla-Nicole Oatu** · Biomedical Engineering master's student at Aalto University

Coursework projects applying Python to energy regression, menstrual health and depression data. Each folder contains the notebooks, required data or access instructions, and an explanation of the analysis.

| Project | Focus | Methods |
| --- | --- | --- |
| [Finnish energy consumption](finland-energy/) | Predict an annual energy measure using socioeconomic variables | Linear regression, Lasso, MAE and R-squared |
| [Menstrual health](menstrual-health/) | Explore sleep and hormones; classify menstrual-cycle phase | Data cleaning, visualisation, Kruskal-Wallis, Spearman correlation, decision trees and random forests |
| [Depression data analysis](depression-analysis/) | Explore MADRS scores and demographics; model follow-up scores and affective type | Exploratory analysis, linear regression and logistic regression |

## Tools

Python, pandas, NumPy, Matplotlib, seaborn, SciPy, scikit-learn and Jupyter.

## Run locally

1. Install Python 3.12 or a compatible version and create a virtual environment.
2. Install the packages: `python -m pip install -r requirements.txt`.
3. Launch `jupyter lab` from the repository folder and open a project notebook.
4. Run the cells in order. The energy and depression CSVs are included. For menstrual health, first obtain the four required files through PhysioNet as described in its README.

## Data and reproducibility

The project files were matched against the original Jupyter coursework workspace. [DATA_SOURCES.md](DATA_SOURCES.md) records what each file is used for and its source status.

The included depression CSV is unchanged from the official **Depresjon** release and is subject to **CC BY-NC 4.0**. The energy table is the original coursework copy; its upstream sources and precise energy-measure definition remain unconfirmed. Restricted mcPHASES participant data, derived participant tables and saved outputs are excluded.

These are small academic experiments. The project READMEs explain the validation performed and the limits of the original methods. Dataset licences apply separately from the analysis code.
