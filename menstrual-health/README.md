# Menstrual health and cycle-phase classification

Explore sleep, hormone measurements and wrist temperature, then classify menstrual-cycle phase using decision trees and random forests.

## Notebooks

- [exploratory_analysis.ipynb](exploratory_analysis.ipynb): cleaning and joining sleep and hormone tables, visualisation, wrist-temperature summaries, Kruskal-Wallis tests and Spearman correlations.
- [phase_classification.ipynb](phase_classification.ipynb): a depth-3 decision tree, a 200-tree random forest using hormones and wrist temperature, and a temperature-only random forest. The target is **cycle phase**, not symptom severity.

## Required data

Obtain mcPHASES through the [official PhysioNet page](https://physionet.org/content/mcphases/), following its access requirements and data use agreement. Place these four files beside the notebooks:

| File | Used by |
| --- | --- |
| `hormones_and_selfreport.csv` | Both notebooks: phase labels, LH, estrogen and PdG |
| `wrist_temperature.csv` | Both notebooks: wrist temperature relative to baseline |
| `sleep.csv` | Exploratory notebook: sleep sessions and duration |
| `sleep_score.csv` | Exploratory notebook: daily sleep quality scores |

These filenames and columns were checked against the original coursework files and local version 1.0.0 archive. The wrist table is approximately 302 MB and the sleep-session table approximately 52 MB. Other large tables such as heart rate, calories and steps are not required by these notebooks.

The work was developed using **version 1.0.0**. PhysioNet now directs users to **version 1.0.1**; that newer release has not been tested here and may require adjustments.

## Data access and citation

The [PhysioNet Restricted Health Data Licence](https://physionet.org/content/mcphases/view-license/1.0.0/) prohibits sharing access to the restricted data. Accordingly, this repository contains **code and documentation only** for this project. Raw participant data, merged participant tables, individual trajectories and saved notebook outputs are excluded. Local derived files such as `sleep_analysis_merged.csv`, `wrist_temp_analysis.csv` and `phase_lengths.csv` are not inputs and must not be uploaded.

Lin, B., Li, J. Y., Kalani, K., Truong, K., and Mariakakis, A. (2025). *mcPHASES: A Dataset of Physiological, Hormonal, and Self-reported Events and Symptoms for Menstrual Health Tracking with Wearables* (version 1.0.0). PhysioNet. [DOI: 10.13026/zx6a-2c81](https://doi.org/10.13026/zx6a-2c81).

## Evaluation limits

The original classifiers split **measurement rows**, not participants. The same participant and day can appear in both train and test sets, especially because wrist temperature contains many readings per day. Scores from this split cannot demonstrate performance on unseen participants. Participant-held-out validation and an explicitly defined measurement unit are needed for that purpose.

Phase labels are hormone-derived, so hormone predictors also require caution. Statistical comparisons and confidence intervals treat repeated observations as independent; they are exploratory rather than confirmatory. Sleep-session alignment and duplicate joins should be examined before interpreting effect sizes.

## Validation and preparation

The four required filenames and column schemas were verified against the local version 1.0.0 dataset. All Python cells passed syntax checks. The full exploratory and classifier notebooks have not been rerun end to end; no new model-performance results are claimed.

The initial inventory now loads only the sleep-analysis inputs rather than all available multi-gigabyte tables. Missing phase values remain missing rather than becoming the text `nan`. Existing fixes include support for the temperature-column spelling, retaining study interval in the classifier join, correcting an undefined dataframe, using the calculated confidence-interval width and correcting output-path messages. The original model choices and splits are retained.
