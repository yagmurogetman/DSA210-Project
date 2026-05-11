# Analysis of Global Cuisines and Climate: The Ingredient Correlation

**Course:** DSA 210 - Introduction to Data Science  
**Student:** Yağmur Ögetman  
**Term:** Spring 2025-2026

## Project Overview

This project investigates whether country-level climate variables are related to global cuisine and ingredient patterns. The analysis combines a global cuisine dataset with standardized climate variables: annual average temperature, relative humidity, and annual precipitation.

The main research question is:

> Are temperature, humidity, and precipitation associated with differences in cuisine and ingredient patterns across countries?

The project originally focused on individual staple ingredients such as rice, potato, and wheat. After merging the datasets, potato and wheat appeared in only one observation each. Therefore, the final interpretation emphasizes broader cuisine-climate patterns and treats individual ingredient tests as exploratory rather than conclusive.

## Dataset

The final merged dataset contains **66 countries**. Each country is represented by one traditional dish and its listed main ingredients. Climate data are merged by `Country_Code`.

Main input files:

| File | Description |
|---|---|
| `global_cuisines_master_final.csv` | Country, representative dish, and main ingredient data |
| `standardized_temperature.csv` | Standardized country-level temperature data |
| `standardized_humidity.csv` | Standardized country-level humidity data |
| `standardized_precipitation.csv` | Standardized country-level precipitation data |

The data processing notebook creates `processed_culinary_climate_data.csv`, where ingredient lists are converted into binary variables. To reduce sparsity, this finalized package also includes `processed_culinary_climate_data_with_categories.csv`, where ingredients are grouped into broader categories.

## Repository Structure

```text
DSA210-Project/
├── README.md
├── requirements.txt
├── global_cuisines_master_final.csv
├── standardized_temperature.csv
├── standardized_humidity.csv
├── standardized_precipitation.csv
├── processed_culinary_climate_data.csv
├── processed_culinary_climate_data_with_categories.csv
├── ingredient_category_summary.csv
├── category_hypothesis_tests.csv
├── data_processing.ipynb
├── data_visulization.ipynb
├── hypothesis_testing.ipynb
├── hypothesis_testing(updated).ipynb
├── ingredient_category_analysis.ipynb
├── ML_Method.ipynb
├── FINAL_REPORT.md
├── FINAL_REPORT.pdf
├── FINAL_PROJECT_EXPLANATION.md
├── SUBMISSION_CHECKLIST.md
└── DSA 210 Project Proposal_ Analysis of Global Cuisines and Climate.pdf
```

Note: `data_visulization.ipynb` and `hypothesis_testing(updated).ipynb` keep their current filenames to preserve the submitted repository history.

## Methodology

### 1. Data Processing

The cuisine and climate datasets are loaded and merged using `Country_Code`. The `Main_Ingredient` column is split into binary ingredient indicators using one-hot encoding.

### 2. Exploratory Data Visualization

The visualization notebook explores relationships between climate variables and ingredient patterns using plots such as scatter plots, boxplots, and heatmaps.

### 3. Hypothesis Testing

The initial hypothesis test compares climate values for countries with different staple ingredients. Rice appears in 17 countries, while Potato and Wheat each appear in only 1 country. Because these individual ingredient counts are imbalanced, ingredient-specific tests are interpreted as exploratory.

To make the analysis more stable, ingredients are also grouped into broader categories:

| Category | Observation Count |
|---|---:|
| Meat_Based | 42 |
| Grain_Based | 37 |
| Vegetable_Based | 27 |
| Spice_Sauce_Based | 16 |
| Dairy_Based | 10 |
| Seafood_Based | 9 |
| Egg_Based | 3 |

### 4. Machine Learning

The machine learning notebook tests whether climate variables can predict whether rice appears as a main ingredient. The models include Decision Tree, Logistic Regression, K-Nearest Neighbors, Random Forest, and K-Means clustering for exploratory grouping.

## Main Results

- Final merged dataset size: **66 countries**
- Rice appears as a main ingredient in **17 countries**
- Potato appears as a main ingredient in **1 country**
- Wheat appears as a main ingredient in **1 country**
- Rice group mean temperature: **18.44°C**
- Potato/Wheat group mean temperature: **19.24°C**
- Welch t-test for Rice vs. Potato/Wheat: **p = 0.9476**

Because the p-value is greater than 0.05, the project fails to reject the null hypothesis. Based on this dataset, there is not enough statistical evidence to conclude that temperature alone creates a significant difference between rice-based and potato/wheat-based cuisines.

The broader category analysis reduces the sparsity problem. It shows that categories such as Grain_Based, Meat_Based, and Vegetable_Based have much larger sample sizes than individual ingredients. Some exploratory category-level patterns appear, especially for humidity, but these should still be interpreted carefully because the dataset is small and country-level.

For the rice prediction task, the best model accuracy is approximately **71%** for Logistic Regression and Random Forest. However, the test set is small, so these results should be interpreted carefully.

## Conclusion

The project suggests that climate variables may provide some exploratory signal for cuisine and ingredient patterns, but the current dataset is too small and imbalanced to support strong causal claims. The small number of Potato and Wheat observations is a dataset limitation, not a coding mistake. The strongest conclusion is that climate may be one factor among many, while cuisine is also shaped by culture, history, agriculture, trade, migration, religion, and regional traditions.

## How to Run

1. Clone or download the repository.
2. Install the required packages:

```bash
pip install -r requirements.txt
```

3. Run the notebooks in this order:

```text
1. data_processing.ipynb
2. data_visulization.ipynb
3. hypothesis_testing.ipynb
4. ingredient_category_analysis.ipynb
5. ML_Method.ipynb
```

## AI Usage Disclaimer

AI assistance was used for code organization, explanation writing, and debugging support. The dataset construction, project direction, interpretation, and final decisions were reviewed and finalized by the student.
