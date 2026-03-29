# DSA 210 Project Proposal: Analysis of Global Cuisines and Climate

**Term:** Spring 2025-2026  
**Student:** Yağmur Ögetman 

---

## Motivation and Objective
The fundamental motivation of this project is to explore how climate, as a primary environmental architect, shapes the **"Culinary DNA"** of nations. Beyond clothing and architecture, human culture is most visceral in gastronomy, which is dictated by cultivable crops and physiological adaptations to heat or cold. 

This research aims to investigate whether a country's average temperature, precipitation, and humidity have a statistically measurable effect on its traditional flavor profiles and macronutrient preferences.

---

## Data Acquisition and Collection Methodology
The data for this study will be integrated from three primary sources:

1. **Global Culinary Data:** Traditional dish data for **60+ countries** will be obtained from **TasteAtlas** (via web scraping) and existing **Kaggle** Global Recipe Datasets. I will target the top 20–30 representative dishes per nation to ensure cultural significance.
2. **Climate Metrics:** National climate data will be retrieved from **The World Bank Climate Change Knowledge Portal (CCKP)** and the **Climatic Research Unit (CRU)**. I will also utilize the **Köppen-Geiger Climate Classification** system to categorize countries into standardized climatic zones (e.g., Tropical, Arid, Continental).
3. **Data Augmentation via AI:** Since raw recipe datasets often lack standardized scores for sensory attributes, I will use **Gemini (LLM)** to annotate the dataset. The model will assign categorical and numerical scores (1-5) for *"Spiciness," "Sweetness,"* and *"Caloric Density"* based on the main ingredients and traditional preparation methods.

---

## Data Characteristics and Samples
* **Sample Size:** The final merged dataset is expected to contain approximately **1,200 to 1,800 unique dishes** spanning over 60 countries across all continents.
* **Features:** The primary features include:
  * `Dish_Name`, `Country`
  * `Mean_Annual_Temperature`, `Precipitation_Levels`
  * `Flavor_Profile_Scores` (Spice/Sweet/Sour)
  * `Predominant_Macronutrient` (Fats/Carbs/Proteins)
* **Processing:** Data will be structured in a tidy format where each row represents a dish-climate pair, allowing for granular correlation analysis.

---

## Hypotheses and Analytical Approach
I will perform **Pearson Correlation Tests** to validate three core hypotheses:

1. **The Spice Defense:** A positive correlation between high ambient temperatures and the usage of antimicrobial spices (pungency levels).
2. **The Caloric Shield:** A negative correlation between annual temperature and fat-rich, calorie-dense meal preferences in colder regions.
3. **The Humidity-Fermentation Link:** Higher seasonal variance and humidity levels correlating with a higher variety of preserved or fermented foods.

## Machine Learning Implementation
* **Decision Tree Classifier:** To predict a country's cuisine category based solely on climate variables.
* **K-Means Clustering:** To identify natural **"Climate-Gastro Zones"** globally and see if they overlap with geographic boundaries.

---

## AI Usage Disclaimer
In this project, AI (**Gemini**) is utilized for:
* **Data Annotation:** Generating flavor scores where raw data is missing or unstructured.
* **Code Optimization:** Assisting in visualization scripts and refining statistical testing frameworks.

---

## Project Structure (Planned)
* `data/`: Raw and processed CSV files.
* `Plots/`: Visual outputs (Heatmaps, Scatter Plots).
* `data_process.ipynb`: Data cleaning and merging.
* `hypothesis_test.ipynb`: Statistical analysis and P-value results.
* `machine_learning.ipynb`: Clustering and classification models.
