# Advanced Python Programming Project

---

## Project Overview
This project implements a data-driven approach following the **CRISP-DM model**, which comprises six stages. The focus is on analyzing a dataset of domestic flights in India to address two key business questions:

1. **Price Prediction**: Can the price of a domestic flight be predicted based on attributes such as route, airline, or date?
2. **Flight Grouping**: Can flights be grouped into clusters based on similarities such as airline, route, or other attributes?

---

## CRISP-DM Stages

### **1. Business Understanding**
- The questions were framed using the SMART model:
  - **Specific:** Defined specific attributes like route, airline, and date.
  - **Measurable:** Focused on measurable outcomes like price or clusters.
  - **Assignable:** Feasible using the available dataset.
  - **Realistic:** Achievable with current data and modeling techniques.
  - **Time-Related:** Focused on specific dates and timelines.

---

### **2. Data Understanding**
- **Dataset Overview:**
  - **Shape:** 11 columns, 13,354 rows.
  - **Key Features:** `Airline`, `Date`, `Source`, `Destination`, `Route`, `Duration`, `Total_Stops`, `Additional_Info`, `Price`.

- **Initial Findings:**
  - Average flight price: ₹8190.64
  - Price range: ₹3.07 to ₹79,512
  - Non-standard formats and duplicates in columns such as `Duration`, `Route`, and `Destination`.
  - `Additional_Info` was deemed uninformative due to inconsistent and redundant values.

- **Visualization Insights:**
  - Price distribution: Skewed, with a wide range from low to high prices.
  - Airlines like Jet Airways dominate expensive flights; Trujet is the cheapest.
  - Non-stop flights tend to be cheaper.
  - Popular months for travel: March; least popular: April.
  - Clear patterns in source-destination relationships.

---

### **3. Data Preparation**
- **Data Cleaning:**
  - Converted `Duration` to minutes for numerical processing.
  - Merged duplicate values (e.g., "New Delhi" and "Delhi").
  - Encoded categorical columns:
    - `Airline` encoded using `LabelEncoder` (0 to 9).
    - `Source` and `Destination` one-hot encoded.
  - Normalized numerical columns for clustering.

- **Feature Engineering:**
  - Extracted segments from `Route` (e.g., `Route 1`, `Route 2`).
  - Grouped `Price` into three categories: low, medium, and high.
  - Added a `Minutes Duration` column for consistent time representation.

- **Challenges and Solutions:**
  - Missing values in `Route` and `Total_Stops`: Removed or filled with appropriate replacements.
  - Balancing categories in `Price`: Identified as an issue for later refinement.

---

### **4. Modeling**
#### **Classification**
- **Goal:** Predict the `Price` category using features such as `Airline`, `Source`, `Destination`, etc.
- **Method:** Classification using training (75%) and test (25%) splits.
- **Performance:**
  - Accuracy: **72.3%**
  - Observed imbalance in `Price` categories:
    - Largest group (low price) dominates predictions.
    - Smallest group (high price) affects model performance.
  - Evaluation Metrics:
    - Used F1-Score for better balance between recall and precision.

#### **Clustering**
- **Goal:** Group flights into similar clusters based on shared attributes.
- **Method:** K-Means clustering with normalized features.
- **Results:**
  - Optimal number of clusters: **3** (determined via elbow method).
  - Silhouette Score: **0.45**, indicating moderate clustering quality.
  - Cluster Characteristics:
    - Distinct separation in `Source` and `Destination`.
    - Overlap observed in `Price` and `Airline`.

---

### **5. Evaluation**
#### **Classification**
- Confusion matrix revealed misclassification, particularly in the high-price category.
- F1-Score highlighted the need for better balancing of `Price` categories.

#### **Clustering**
- Visualization of clusters showed clear grouping in `Source` and `Destination` attributes.
- Overlap in `Price` clusters suggests additional features may improve separation.

---

### **6. Conclusion**
- **Classification:**
  - Achieved moderate accuracy but requires balanced data for better prediction reliability.
  - Suggestions:
    - Address imbalance in `Price` categories (e.g., resampling techniques).
    - Experiment with alternative algorithms for improvement.

- **Clustering:**
  - Successfully grouped flights into three clusters based on similarities.
  - Findings:
    - `Source` and `Destination` are primary drivers for cluster differentiation.
    - Further feature refinement can improve results.

---

## Key Learnings and Future Directions
- Data quality is crucial: Addressing duplicates, missing values, and standardizing formats improved outcomes significantly.
- Balancing datasets: Necessary for both classification and clustering models.
- Future Work:
  - Implement advanced balancing techniques for classification.
  - Explore other clustering methods for more nuanced results.
