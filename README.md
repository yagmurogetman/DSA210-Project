# Analysis of Global Cuisines and Climate: The Ingredient Correlation

**Term:** Spring 2025-2026  
**Student:** Yağmur Ögetman  
**Course:** DSA 210 - Introduction to Data Science

---

## 1. Motivation and Objective
[cite_start]The core motivation of this project is to analyze how climate, as a primary environmental architect, shapes the **"Culinary DNA"** of nations through their choice of ingredients[cite: 5]. [cite_start]Rather than focusing on subjective taste preferences, this research investigates the direct relationship between environmental metrics and the **specific ingredient profiles** used in traditional global dishes[cite: 7].

[cite_start]The objective is to utilize data science to determine if a country's climate—measured by temperature, precipitation, and humidity—statistically predicts the prevalence of specific ingredients in its traditional gastronomy[cite: 7, 8].

## 2. Data Acquisition and Methodology
The study integrates data from three primary pillars:

* [cite_start]**Global Culinary Data:** Traditional ingredient data for **60+ countries** obtained from **TasteAtlas** and **Kaggle Global Recipe Datasets**, targeting the most representative dishes per nation[cite: 12, 13].
* [cite_start]**Climate Metrics (2000-2024):** National climate data, including mean annual temperature and humidity, retrieved from **The World Bank Climate Change Knowledge Portal (CCKP)** and the **Climatic Research Unit (CRU)**[cite: 14, 15].
* [cite_start]**Data Processing via AI:** Using **Gemini (LLM)** to extract and categorize unstructured ingredient lists into a standardized format for statistical analysis[cite: 19, 47].

## 3. Data Characteristics
[cite_start]The finalized dataset contains approximately **1,200 to 1,800 unique dishes** mapped to their respective national climate profiles[cite: 22, 26].

| Category | Features |
| :--- | :--- |
| **Geographic** | [cite_start]Country Name, Region, Köppen-Geiger Climate Zone [cite: 24] |
| **Climate Data** | [cite_start]Mean Annual Temp (°C), Annual Precipitation (mm), Relative Humidity (%) [cite: 24] |
| **Ingredient Profile** | [cite_start]Specific Ingredient Presence (Binary/Frequency), Dominant Base Ingredients [cite: 24] |
| **Nutritional** | [cite_start]Predominant Macronutrient (Fats/Carbs/Proteins), Caloric Density [cite: 24] |

## 4. Research Hypotheses
1.  [cite_start]**The Ingredient-Climate Link:** A statistically measurable correlation exists between high ambient temperatures and the prevalence of specific antimicrobial or heat-resistant ingredients[cite: 30, 31].
2.  [cite_start]**The Caloric Balance:** A negative correlation between annual temperature and the use of high-fat, calorie-dense ingredients in traditional meal preparation[cite: 32].
3.  [cite_start]**Preservation through Ingredients:** Regions with higher humidity and seasonal variance show a higher reliance on ingredients associated with traditional preservation and fermentation[cite: 33].

## 5. Machine Learning Implementation
* [cite_start]**Pearson Correlation:** To validate the strength of the relationship between climate variables and ingredient usage[cite: 29].
* [cite_start]**Decision Tree Classifier:** To predict the dominant ingredient profile of a cuisine based solely on climate inputs[cite: 36].
* [cite_start]**K-Means Clustering:** To identify **"Climate-Gastro Zones"** and visualize whether countries with similar climates share a common "ingredient vocabulary" regardless of geographic distance[cite: 37].

## 6. Project Structure
* [cite_start]`data/`: Raw and processed ingredient-climate datasets[cite: 39].
* [cite_start]`plots/`: Visual outputs including Heatmaps and distributions (e.g., Temperature vs. Ingredient Groups)[cite: 42].
* [cite_start]`data_process.ipynb`: Data scraping, ingredient cleaning, and dataset merging[cite: 43].
* [cite_start]`hypothesis_test.ipynb`: Statistical analysis and P-value results[cite: 44].
* [cite_start]`machine_learning.ipynb`: Clustering and classification models[cite: 45].

## 7. AI Usage Disclaimer
[cite_start]AI (Gemini) is utilized for **Data Annotation** (extracting and categorizing ingredients from unstructured text) and **Code Optimization** for complex statistical visualizations[cite: 47, 48, 49].
