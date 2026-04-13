# Analysis of Global Cuisines and Climate: The Ingredient Correlation

**Term:** Spring 2025-2026  
**Student:** Yağmur Ögetman  
**Course:** DSA 210 - Introduction to Data Science  

---

## 1. Motivation and Objective

The fundamental motivation of this project is to explore how climate, as a primary environmental architect, shapes the "Culinary DNA" of nations. Instead of focusing on subjective flavor profiles, this research investigates the direct correlation between environmental stressors and the specific ingredients used in traditional dishes.

Human gastronomy is often dictated by cultivable crops and local biodiversity. This project aims to bridge the gap between environmental science and food sociology by analyzing whether climate metrics (temperature, precipitation, humidity) statistically dictate the presence of specific ingredient groups (e.g., grains, tubers, proteins, or preservative agents).

---

## 2. Data Acquisition and Methodology

The dataset is integrated from three primary dimensions:

- **Global Culinary Data:** Scraped from TasteAtlas and curated from Kaggle Global Recipe Datasets, covering 60+ countries with 20–30 representative dishes per nation.  
- **Climate Metrics (2000–2024):** Retrieved from The World Bank Climate Change Knowledge Portal (CCKP) and the Climatic Research Unit (CRU).  
- **Ingredient Mapping:** Ingredients are extracted and categorized to identify correlations with specific climate zones (Köppen-Geiger Classification).

---

## 3. Data Characteristics

The final merged dataset contains approximately **1,200 to 1,800 unique dishes** with the following features:

| Category        | Features |
|----------------|----------|
| Geographic     | Country Name, Region, Köppen-Geiger Climate Zone |
| Climate        | Mean Annual Temp (°C), Annual Precipitation (mm), Relative Humidity (%), Seasonal Variance |
| Ingredient Data| Presence of Staple Crops (Rice, Wheat, Potato, Maize), Protein Sources, Preservatives |
| Nutritional    | Predominant Macronutrient, Estimated Caloric Density |

---

## 4. Research Hypotheses

- **The Staple Shift:**  
  There is a significant correlation between mean annual temperature/precipitation and the dominant staple ingredient (e.g., rice-dominant vs. wheat-dominant regions).

- **The Caloric Shield:**  
  There is a negative correlation between annual temperature and the prevalence of fat-rich, calorie-dense ingredients in traditional diets.

- **Preservation Patterns:**  
  Higher relative humidity and seasonal variance correlate with a higher frequency of ingredients associated with long shelf life or traditional preservation methods.

---

## 5. Machine Learning & Statistical Analysis

- **Pearson Correlation & Multivariate Regression:**  
  Used to validate relationships between climate variables and ingredient frequency.

- **Decision Tree Classifier:**  
  Predicts a country’s dominant ingredient profile based solely on climate variables.

- **K-Means Clustering:**  
  Identifies "Climate-Gastro Zones" where geographically distant countries share similar ingredient patterns due to similar climates.

---

## 6. Project Structure
