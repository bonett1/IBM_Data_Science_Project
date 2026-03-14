# 🚀 SpaceX Falcon 9 — First Stage Landing Prediction

> Final project for the **IBM Data Science Professional Certificate**  
> Predicting whether the Falcon 9's first stage will land successfully to cut costs through reusability.

[![Python](https://img.shields.io/badge/Python-3.x-blue?logo=python)](https://www.python.org/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange?logo=jupyter)](https://jupyter.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

---

## 📋 About

SpaceX's big competitive advantage is reusing the Falcon 9's first stage booster — bringing costs down from ~$165M to ~$62M per launch. This project builds a Machine Learning model to **predict whether a landing will succeed**, helping competitors estimate launch costs more accurately and avoid costly bids on unfavorable conditions.

---

## 🗂️ Pipeline Overview

1. Data Collection (REST API + Web Scraping)
2. Data Wrangling & Cleaning
3. Exploratory Data Analysis (SQL + Visualization)
4. Geospatial Analysis (Folium)
5. Interactive Dashboard (Plotly Dash)
6. Predictive Modeling (Classification)

---

## 📦 Data Collection

### REST API
- Fetched launch data from SpaceX's official API (`v4/launches`)
- Decoded JSON responses with `pd.json_normalize()`
- Filtered for Falcon 9 launches only
- Handled nulls and data types

### Web Scraping
- Scraped Falcon 9 launch history from Wikipedia
- Parsed HTML with **BeautifulSoup**
- Mapped headers and rows into a structured DataFrame

---

## 🔧 Data Wrangling

| Step | Description |
|---|---|
| Missing Values | Identified with `.isnull()` |
| Imputation | Filled `PayloadMass` with column mean |
| Binary Mapping | `Class`: 1 = Success, 0 = Failure |
| Encoding | One-Hot Encoding on categorical variables |

---

## 📊 Exploratory Data Analysis

### SQL
- **CCAFS SLC-40** handles the highest launch volume
- Queries to find total payload mass and critical weight ranges
- Pinpointed the exact first successful ground landing

### Visualization (Python)
- Success rate improves as flight number increases (operational maturity)
- Orbits **ES-L1, GEO, HEO, and SSO** have a 100% historical success rate
- Heavy payloads are almost exclusively launched from **KSC LC-39A**

---

## 🗺️ Geospatial Analysis

Built interactive maps with **Folium** to explore launch sites:

- Coastal positioning keeps debris drops over the ocean
- All sites are within < 1km of railways and highways for booster transport
- Safely distanced from densely populated urban areas

---

## 📈 Interactive Dashboard

Built with **Plotly Dash**:

- **KSC LC-39A** has the best success-to-launch ratio
- Sweet spot payload range: **0–5,000 kg** shows the highest landing success concentration

---

## 🤖 Predictive Modeling

All models were tuned with **GridSearchCV**.

| Model | Accuracy (Test Set) |
|---|---|
| Logistic Regression | 83.3% |
| SVM | 83.3% |
| Decision Tree | **83.3%** ⭐ |
| KNN | 83.3% |

> ✅ **Recommended model:** Decision Tree — same accuracy, but way easier to explain to stakeholders.

---

## 🔑 Key Takeaways

- **Best launch site:** KSC LC-39A consistently delivers the highest landing success rate
- **Experience matters:** Success rate grows with flight number, proving iterative engineering works
- **Solid predictions:** All ML models hit **83.3% accuracy** on unseen data

---

## 🛠️ Tech Stack

- `Python` · `Pandas` · `NumPy` · `Scikit-learn`
- `BeautifulSoup` · `Requests`
- `Folium` · `Plotly Dash` · `Matplotlib` · `Seaborn`
- `SQL` (Jupyter + SQLite/DB2)

---

## 👤 Author

**Pedro Bonetti**  
[![GitHub](https://img.shields.io/badge/GitHub-bonett1-black?logo=github)](https://github.com/bonett1)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-pedro--bonetti-blue?logo=linkedin)](https://linkedin.com/in/pedro-bonetti)

---

*Capstone project for the IBM Data Science Professional Certificate.*
