# FlightPrediction
Data-Driven Final Project: Advanced Python Programming

## Overview
This project implements advanced data analysis techniques on flight data using Python, following the CRISP-DM methodology. The project answers two main business questions through data preprocessing, classification, and clustering.


## Goals
1. **Predict Flight Prices:** Estimate the price of domestic flights in India using features like airline, route, and date.
2. **Cluster Flights:** Group flights into clusters based on similarities (e.g., airline, route).



## Methodology: CRISP-DM

### 1. Business Understanding
- Defined goals using the SMART framework for clarity and realism.
- Questions focus on price prediction and clustering flights.

### 2. Data Understanding
- **Dataset:** 11 columns, 13,354 rows.
- Key issues:
  - Missing and inconsistent values in columns like `Airline` and `Route`.
  - Wide price range (₹3.07 to ₹79,512).
- **Exploratory Data Analysis (EDA):**
  - Revealed insights into flight patterns, durations, and costs.

### 3. Data Preparation
- **Preprocessing steps:**
  - Removed redundant columns (`Date`, `Additional_Info`).
  - Cleaned and encoded categorical data (e.g., airline names unified using `LabelEncoder`).
  - Converted flight durations to minutes (`Minutes Duration`).
  - Balanced data for classification tasks.
- **Key Insights:**
  - Jet Airways is the most expensive airline, Trujet the cheapest.
  - Kolkata is the least expensive destination.

### 4. Modeling
#### Classification:
- Built models to predict flight price categories (low, medium, high).
- **Accuracy:** ~72.3%.
- **Challenge:** Imbalanced dataset impacted predictions for high-price flights.

#### Clustering:
- Applied KMeans to group flights.
- **Optimal clusters:** **3** (based on elbow and silhouette methods).
- Strong alignment with `Source` and `Destination`.

### 5. Evaluation
#### Classification:
- F1-score used for imbalanced data evaluation.
- Recommendations: Balance data for better predictions.

#### Clustering:
- Silhouette score: 0.45.
- Visualizations confirmed clustering aligns with flight routes.

### 6. Conclusions
- **Classification:** Requires balanced data for improved results.
- **Clustering:** Successfully groups flights by route, origin, and destination.

---

## Visualizations
- **EDA plots:** Price distribution, flight frequencies by airline.
- **Clustering results:** KMeans with optimal clusters.

---

## Repository Contents
- **`scripts/`**: Python scripts for data cleaning, EDA, and modeling.
- **`notebooks/`**: Jupyter notebooks documenting each step.
- **`data/`**: Preprocessed datasets and raw data (if permissible).
- **`visualizations/`**: Graphs and plots generated during the analysis.

---

## Key Technologies
- **Python Libraries:**
  - `pandas`, `numpy`, `matplotlib`, `seaborn` for data manipulation and visualization.
  - `sklearn` for machine learning models (classification, clustering).
- **CRISP-DM Framework** for structured analysis.

---

## Installation and Usage
1. Clone the repository:
   ```bash
   git clone <repository_url>
   ```
2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
3. Explore the notebooks and scripts for detailed analysis steps.

---

## Authors
- **Or Zamir**  
---

## License
This project is licensed under the MIT License - see the LICENSE file for details.

---
