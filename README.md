# Global Military Strength & Power Clustering

An end-to-end unsupervised machine learning project that analyzes global military power indicators, defense spending, manpower, and strategic resources across 138 nations. The project applies **K-Means Clustering**, **Hierarchical Clustering (Dendrogram)**, and **Principal Component Analysis (PCA)** to categorize countries into distinct military power tiers.

---

## Project Overview

Understanding the geopolitical and military balance between nations requires analyzing a complex set of features ranging from aircraft and naval fleets to logistical manpower and economic constraints. 

In this study:
1. Raw military indicators from the **Global Firepower / World Military Power** dataset were cleaned and transformed.
2. Exploratory Data Analysis (EDA) was conducted to evaluate the *Military Strength Power Index*.
3. The optimal number of clusters ($K=4$) was determined using the **Elbow Method (KElbowVisualizer)**.
4. **K-Means** and **Hierarchical Clustering** algorithms were trained and evaluated using the **Silhouette Score**.
5. High-dimensional feature space was projected onto 2D space using **PCA** for cluster visualization.

---

##  Dataset & Features

The dataset comprises **138 countries** evaluated across **30+ quantitative metrics**, including:
* **Air Power:** Aircraft Strength, Fighter/Interceptor, Attack Aircraft, Helicopters.
* **Land Power:** Tank Strength, AFV/APC, Artillery, Rocket Projectors.
* **Naval Power:** Fleet Strength, Aircraft Carriers, Submarines, Destroyers, Frigates.
* **Logistics & Geography:** Available Manpower, Total Population, Coastline, Waterways, Border Coverage.
* **Economic & Strategic Resources:** Defense Spending Budget, External Debt, Oil Production/Consumption, Proven Reserves.

---

##  Data Preprocessing & Pipeline

* **Data Cleaning:** Stripped string formatting, commas, and invalid symbols across monetary and demographic columns.
* **Type Conversion:** Converted all feature attributes into proper numerical (`float64`/`int64`) formats.
* **Missing Value Handling:** Handled non-coastal / landlocked attributes and missing strategic data via zero-imputation.
* **Feature Scaling:** Applied standard scaling (`StandardScaler`) to eliminate variance skew between billion-dollar economic indicators and single-digit naval counts.

---

##  Methodology & Results

### 1. Optimal Cluster Determination (Elbow Method)
Using the `yellowbrick` KElbowVisualizer across $K \in [2, 15]$, an optimal distortion elbow was identified at **$K = 4$**.

### 2. Model Evaluation (Silhouette Analysis)
* **Silhouette Score:** `~0.87` (indicating well-separated, cohesive, and dense cluster groupings).

### 3. Dimensionality Reduction (PCA)
* Extracted the top 2 principal components to capture major variance across defense attributes and visualize multi-dimensional cluster separations in 2D scatter plots.

---

##  Tech Stack

* **Language:** Python
* **Data Manipulation:** `pandas`, `numpy`
* **Machine Learning:** `scikit-learn` (`KMeans`, `PCA`, `StandardScaler`, `silhouette_score`)
* **Clustering Analysis:** `scipy.cluster.hierarchy` (`linkage`, `dendrogram`), `yellowbrick`
* **Visualization:** `matplotlib`, `seaborn`

---

##  Getting Started

### 1. Clone the repository
```bash
git clone [https://github.com/](https://github.com/)<your-username>/world-military-power-clustering.git
cd world-military-power-clustering
