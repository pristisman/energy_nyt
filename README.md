# Energy Policy in Flux: An NLP Approach to Media Discourse Before and After the Russia-Ukraine Conflict

## Abstract  
This paper explores shifts in the discourse surrounding energy policy by applying natural language processing (NLP) techniques to \textit{New York Times} articles published between 2021 and 2023. Using dictionary-based analysis, topic modeling methods—including Latent Dirichlet Allocation (LDA) and Structural Topic Modeling (STM)—as well as a time series regression analysis, I examine whether the prominence and framing of energy-related issues changed after the onset of the Russia-Ukraine war. The results indicate that energy-related topics became significantly more prominent following the conflict, though their salience gradually declined over time, suggesting a normalization of coverage or a shift in media focus.

## Repository Structure

This repository contains the code, data, and outputs necessary to reproduce the analyses, figures, and results in the paper.

### 1. `code/` Folder

Contains all the scripts needed to process data, run models, and generate results.

- **`energy_nyt.qmd`**: Main script to run all models and reproduce final results, tables, and figures in the paper.

#### Subfolder: `intermediate_steps/`

This folder contains supporting scripts used during model development on different data subsets.
These scripts were used to produce intermediate models that helped in selecting the final models.
The models here were fine-tuned later based on these initial experiments.
Please note that the scripts may not be fully polished or perfectly tidy, as they were primarily intended for exploration and defining the best-performing models.

#### Main Files:

- **`1.0.build_dataset.qmd`**
  - **Inputs**: `nyt_metadata.csv`
  - **Purpose**: Loads and filters articles from 2021–2023, producing annual and combined datasets.
  - **Outputs**:
    - `nyt_2021.csv`
    - `nyt_2022.csv`
    - `nyt_2023.csv` (saved in `data/`)
    - `nyt_combined_2021_2023.csv` (available via [Box](https://georgetown.app.box.com/folder/317619628250))

- **`1.1.exploratory_data_analysis.qmd`**
  - **Inputs**: `nyt_combined_2021_2023.csv`
  - **Purpose**: Exploratory analysis of NYT articles (word frequencies, word clouds, sentiment analysis) by year and war period.
  - **Outputs**: Summary statistics and plots.

- **`2.0.topic_modelling_all.qmd`**
  - **Inputs**: `nyt_combined_2021_2023.csv`
  - **Purpose**: Topic modeling on all energy-related articles from 2021–2023.
  - **Outputs**: LDA/STM topic models and visualizations (pre/post war).

- **`2.1.topic_modeling_policy.qmd`**
  - **Inputs**: `nyt_combined_2021_2023.csv`
  - **Purpose**: Topic modeling focused on energy policy articles.
  - **Outputs**: Topic visualizations comparing narratives over time.

- **`3.0.interrupted_time_series.qmd`**
  - **Inputs**: `nyt_combined_2021_2023.csv`
  - **Purpose**: Runs regression analyses, including interrupted time series.
  - **Outputs**: Regression tables and model summaries.

---

### 2. `data/` Folder

Contains the following datasets built using `1.0.build_dataset.qmd`:

- `nyt_2021.csv`  
- `nyt_2022.csv`  
- `nyt_2023.csv`  

> 🔗 `nyt_combined_2021_2023.csv` is available [here](https://georgetown.app.box.com/folder/317619628250) and should be downloaded into the `data/` folder to run the main analysis.

---

### 3. `figures/` Folder

Contains all visual outputs generated for the paper:

- Topic model visualizations  
- Sentiment analysis plots  
- Regression figures  
- Word clouds and keyword frequency plots  

---

