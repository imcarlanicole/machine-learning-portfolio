# Menstrual health and cycle-phase classification

Explore relationships among sleep, hormone measurements and wrist temperature, then classify menstrual-cycle phase with decision-tree and random-forest models.

## Notebooks

- [`exploratory_analysis.ipynb`](exploratory_analysis.ipynb): data cleaning, wearable-data joins, sleep and hormone plots, wrist-temperature summaries, Kruskal-Wallis tests and Spearman correlations.
- [`phase_classification.ipynb`](phase_classification.ipynb): a depth-3 decision tree, a 200-tree random forest using hormones and wrist temperature, and a temperature-only random forest. The target is menstrual-cycle phase, not symptom severity.

## Data

The notebooks use mcPHASES. Obtain data through the [official PhysioNet resource](https://physionet.org/content/mcphases/) under its access terms. The local source archive was labelled version 1.0.0; a different release may require column-name adjustments.

Place `hormones_and_selfreport.csv`, `wrist_temperature.csv`, `sleep.csv` and `sleep_score.csv` beside the notebooks. The exploratory notebook also inventories optional CSV tables listed in its opening cells. Participant data, derived CSV files and saved notebook outputs are excluded from the repository.

Dataset reference: Lin, B., Li, J. Y., Kalani, K., Truong, K., & Mariakakis, A. (2025). *mcPHASES: A Dataset of Physiological, Hormonal, and Self-reported Events and Symptoms for Menstrual Health Tracking with Wearables* (version 1.0.0). PhysioNet. [DOI: 10.13026/zx6a-2c81](https://doi.org/10.13026/zx6a-2c81).

## Evaluation limits

The classifiers retain the original stratified 80/20 split of rows. Repeated measurements from the same participant can therefore appear in both sets; this does not measure generalization to unseen participants. Participant-held-out validation is needed for that question. Hormone-based predictors also require careful interpretation if the phase labels were determined from hormone measurements.

Statistical comparisons and confidence intervals treat observations as independent, although measurements repeat within participants. They are exploratory and should be revisited with methods that account for repeated measures. Sleep-session joins and study-interval alignment also need validation against the data dictionary.

## Preparation notes

Saved outputs were cleared. The temperature-only model now uses the dataframe created in the same notebook; alternate temperature-column spellings are accepted. The classifier join retains study interval when it exists in both tables. Confidence-interval bars now use their calculated width rather than being enlarged fivefold. An undefined plotting variable and a misleading export-path message were corrected in the exploratory notebook. These copies have been checked for Python syntax but have not been rerun on the source data.
