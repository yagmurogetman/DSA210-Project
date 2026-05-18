# Final Report: Analysis of Global Cuisines and Climate

**Student:** Yağmur Ögetman  
**Course:** DSA 210 - Introduction to Data Science  
**Project:** Analysis of Global Cuisines and Climate: The Ingredient Correlation

## 1. Introduction

This project examines whether climate variables are related to global cuisine and ingredient patterns. The motivation is based on the idea that food culture is influenced not only by cultural preferences, but also by environmental conditions such as temperature, humidity, and precipitation. These environmental conditions affect agriculture, crop availability, and long-term dietary habits.

The main research question is:

**Are temperature, humidity, and precipitation associated with differences in cuisine and ingredient patterns across countries?**

The project initially focused on specific staple ingredients such as rice, potato, and wheat. However, after merging the cuisine and climate datasets, potato and wheat appeared in very few observations. Therefore, the final report treats individual ingredient tests as exploratory and emphasizes broader cuisine-climate patterns.

## 2. Data Description

The project uses four CSV files. The cuisine dataset contains 66 countries, each with a representative dish and its listed main ingredients. The climate datasets contain standardized country-level values for temperature, humidity, and precipitation. These datasets are merged using the `Country_Code` column.

After merging, the final dataset includes 66 observations. The `Main_Ingredient` column is transformed into binary ingredient indicators using one-hot encoding. For example, if a country dish contains rice, the `Rice` column is coded as 1; otherwise, it is coded as 0.

Key dataset summary:

| Item | Value |
|---|---:|
| Number of countries | 66 |
| Number of binary ingredient columns | 79 |
| Countries with Rice as main ingredient | 17 |
| Countries with Potato as main ingredient | 1 |
| Countries with Wheat as main ingredient | 1 |

The individual ingredient counts show that some ingredient-level groups are too small for reliable statistical testing. To address this limitation, ingredients were also grouped into broader categories such as grain-based, meat-based, seafood-based, vegetable-based, dairy-based, spice/sauce-based, and egg-based ingredients.

## 3. Data Processing

The data processing stage loads the cuisine and climate datasets, selects the relevant columns, merges them by country code, and creates binary ingredient variables from the ingredient lists. The merged dataset is saved as `processed_culinary_climate_data.csv`.

A second processed dataset, `processed_culinary_climate_data_with_categories.csv`, is also included in the finalized package. This version groups sparse individual ingredients into broader categories. This step reduces the problem of having only one observation for some individual ingredients.

The broader ingredient category counts are:

| Ingredient Category | Observation Count |
|---|---:|
| Meat_Based | 42 |
| Grain_Based | 37 |
| Vegetable_Based | 27 |
| Spice_Sauce_Based | 16 |
| Dairy_Based | 10 |
| Seafood_Based | 9 |
| Egg_Based | 3 |

## 4. Exploratory Data Analysis

The visualization notebook explores ingredient-climate relationships using plots. These visualizations compare the climate distributions of countries with different ingredient patterns and help identify whether visible differences exist before formal hypothesis testing.

The exploratory analysis suggests that climate can be a useful lens for comparing cuisines, but no single climate variable fully explains ingredient patterns. This is expected because cuisine is also influenced by culture, religion, trade routes, colonization, migration, agricultural history, and economic factors.

## 5. Hypothesis Testing

The original hypothesis test was designed to compare temperature values for rice-based and potato-based cuisines. However, the potato group contains only one country in the merged dataset. The wheat group also contains only one country. Therefore, a direct Rice vs. Potato or Rice vs. Wheat test is not statistically reliable.

The revised hypothesis test is stated as follows:

- **Null hypothesis (H0):** There is no significant difference in annual average temperature between rice-based cuisines and potato/wheat-based cuisines.
- **Alternative hypothesis (H1):** There is a significant difference in annual average temperature between rice-based cuisines and potato/wheat-based cuisines.

The Rice group contains 17 countries and has an average temperature of 18.44°C. The Potato/Wheat group contains 2 countries and has an average temperature of 19.24°C. Welch's independent two-sample t-test gives a p-value of 0.9476.

Since the p-value is greater than 0.05, the null hypothesis is not rejected. Therefore, this dataset does not provide statistically significant evidence that temperature alone creates a difference between rice-based and potato/wheat-based cuisines.

This result should be interpreted carefully. The lack of statistical significance does not prove that climate has no effect. It only means that the current dataset is too small and imbalanced to confirm a strong relationship for these specific ingredients.

## 6. Broader Ingredient Category Analysis

Because individual ingredients such as potato and wheat appeared in very few observations, a broader category-level analysis was added. This groups similar ingredients into categories such as Grain_Based, Meat_Based, Vegetable_Based, Dairy_Based, Seafood_Based, and Spice_Sauce_Based.

This modification makes the analysis stronger because the category groups have larger sample sizes than individual ingredient groups. For example, Grain_Based ingredients appear in 37 countries, Meat_Based ingredients appear in 42 countries, and Vegetable_Based ingredients appear in 27 countries.

Welch tests were also calculated for category-level comparisons across temperature, humidity, and precipitation. Some exploratory differences appear, especially in humidity for meat-based and seafood-based categories. However, these findings should not be interpreted as definitive because the dataset is still small, country-level, and based on one representative dish per country.

The purpose of this addition is not to force a significant result, but to handle the sparsity problem more responsibly and show that the project recognizes the limitation of individual ingredient counts.

## 7. Machine Learning Results
**Commit ID:** 823da14

This commit represents the Machine Learning / Method part of the project completed and submitted on May 5, 2026.

The machine learning task predicts whether rice appears as a main ingredient using three climate variables: temperature, humidity, and precipitation.

| Model | Accuracy |
|---|---:|
| Decision Tree | 0.50 |
| Logistic Regression | 0.71 |
| K-Nearest Neighbors | 0.64 |
| Random Forest | 0.71 |

Logistic Regression and Random Forest produced the highest test accuracy, approximately 71%. However, the test set contains only 14 countries, so the accuracy should not be interpreted as a strong general result.

The Random Forest model distributes feature importance relatively evenly across temperature, humidity, and precipitation. This suggests that ingredient patterns may not be explained by one climate variable alone. In the Logistic Regression model, precipitation has a positive coefficient for rice prediction, while humidity has a negative coefficient. These findings suggest possible climate signals, but they require a larger dataset for stronger validation.

## 8. Clustering Analysis

K-Means clustering was used to group countries based on climate and ingredient variables. Four clusters were selected as exploratory culinary-climate zones. Most countries were grouped into one large cluster, while a few countries formed individual smaller clusters. This indicates that the dataset may be too small or too sparse for stable clustering. The clustering analysis is useful as an exploratory visualization, but it should not be treated as a final classification of cuisines.

## 9. Limitations

The main limitation of this project is dataset size. Each country is represented by only one dish, which cannot fully capture the diversity of a national cuisine. In addition, some ingredients appear in very few countries, making statistical tests difficult. For example, Potato and Wheat each appear in only one country in this dataset.

This is a limitation of the dataset, not a coding mistake. The project identifies this issue and avoids making strong claims from these categories. Instead, the analysis shifts toward broader ingredient categories and careful interpretation.

Another limitation is that cuisine is influenced by many non-climate factors, such as culture, religion, trade routes, colonization, migration, economic development, and agricultural policy. Climate can be one explanatory factor, but it is not the only driver of food traditions.

## 10. Conclusion

Overall, this project explored the relationship between global cuisine patterns and climate variables using country-level cuisine and climate datasets. Temperature, humidity, and precipitation were analyzed as possible explanatory factors for cuisine-related differences.

The results suggest that climate variables may provide useful exploratory insights into global cuisine patterns. However, the findings should not be interpreted as causal or definitive because the final dataset is relatively small and some ingredient categories are highly imbalanced. In particular, potato and wheat appeared in very few observations, which limited the reliability of ingredient-level hypothesis testing.

The category-level analysis improves the project by reducing ingredient sparsity and shifting the focus from very small individual ingredient groups to broader cuisine patterns. The strongest conclusion is that climate may be associated with cuisine patterns, but stronger conclusions would require a larger and more balanced dataset with multiple dishes per country and more detailed regional information.

## 11. Reproducibility

The notebooks should be run in this order:

1. `data_processing.ipynb`
2. `data_visulization.ipynb`
3. `hypothesis_testing.ipynb`
4. `ingredient_category_analysis.ipynb`
5. `ML_Method.ipynb`

The required Python packages are listed in `requirements.txt`.
