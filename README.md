# DSA 210 Project Proposal: Analysis of Global Cuisines and Climate

**Term:** Spring 2025-2026  
**Student:** Yağmur Ögetman  

---

## 1. Motivation and Objective
The fundamental motivation of this project is to explore how climate, as a primary environmental architect, shapes the **"Culinary DNA"** of nations. Human culture is most visceral in gastronomy, which is often dictated by cultivable crops and physiological adaptations to environmental stressors.

This research aims to investigate whether a country's climate metrics—specifically **average temperature, precipitation, and humidity**—have a statistically measurable effect on its traditional flavor profiles and macronutrient preferences.

---

## 2. Data Acquisition and Collection Methodology
The data for this study will be integrated from three primary sources:

* **Global Culinary Data:** Traditional dish data for **60+ countries** will be obtained from **TasteAtlas** (via web scraping) and existing **Kaggle Global Recipe Datasets**. I will target the top 20–30 representative dishes per nation.
* **Climate Metrics:** National climate data will be retrieved from **The World Bank Climate Change Knowledge Portal (CCKP)** and the **Climatic Research Unit (CRU)**. To ensure historical relevance to traditional recipes, I will use mean climate data from the **2000–2024 period**.
* **Data Augmentation via AI:** Since raw recipe datasets often lack standardized scores for sensory attributes, I will use **Gemini (LLM)** to annotate the dataset. The model will assign scores (1-5) for **"Spiciness," "Sweetness,"** and **"Caloric Density"**.

---

## 3. Data Characteristics and Samples
The final merged dataset will contain approximately **1,200 to 1,800 unique dishes**.

### Feature Set
| Category | Specific Features |
| :--- | :--- |
| **Geographic** | Country Name, Region, Köppen-Geiger Climate Zone |
| **Climate (2000-2024)** | Mean Annual Temp (°C), Annual Precipitation (mm), **Relative Humidity (%)**, Seasonal Variance |
| **Flavor Profile** | Spiciness (1-5), Sweetness (1-5), Sourness (1-5), Fermentation (Binary) |
| **Nutritional** | Predominant Macronutrient, Estimated Caloric Density |

---

## 4. Hypotheses
1.  **The Spice Defense:** A positive correlation between high ambient temperatures/humidity and the usage of antimicrobial spices.
2.  **The Caloric Shield:** A negative correlation between annual temperature and fat-rich, calorie-dense meal preferences.
3.  **The Humidity-Fermentation Link:** Higher relative humidity levels correlate with a higher variety of preserved or fermented foods.

---

## 5. Machine Learning Implementation
* **Decision Tree Classifier:** To predict a country's cuisine category based on climate variables.
* **K-Means Clustering:** To identify natural **"Climate-Gastro Zones"** and compare them with geographic boundaries.

---

## 6. Project Structure (Planned)
* `data/`: Raw and processed CSV files.
* `plots/`: Heatmaps, Scatter Plots, and Cluster Visualizations.
* `data_process.ipynb`: Data cleaning, scraping, and merging.
* `hypothesis_test.ipynb`: Statistical analysis and P-value results.
* `machine_learning.ipynb`: Clustering and classification models.

---

## 7. AI Usage Disclaimer
AI (Gemini) is utilized for:
* **Data Annotation:** Generating flavor/caloric scores where raw data is unstructured.
* **Code Optimization:** Refining visualization scripts and statistical testing frameworks.
