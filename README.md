# Instacart Market Basket Analysis Project

## 📌 Project Overview
This project aims to predict which products a user will purchase again in their next order based on their historical behavior. Using the Instacart dataset (3 million grocery orders from 200,000 users), we developed a machine learning pipeline that covers data cleaning, feature engineering, and high-performance modeling.

## 📂 Project Structure
```text
.
├── data/
│   └── raw/                 # Store raw CSV files here (from Kaggle)
├── notebooks/
│   ├── 01_data_cleaning.ipynb      # Step 1: Preprocessing & Memory Optimization
│   ├── 02_eda_user_behavior.ipynb  # Step 2: User-level analysis
│   ├── 03_eda_products_stats.ipynb # Step 3: Product-level analysis
│   ├── 04_feature_engineering.ipynb # Step 4: Generating predictive features
│   └── 05_modeling_evaluation.ipynb # Step 5: Model training & evaluation
├── requirements.txt         # Required Python libraries
└── README.md                # Project documentation
```

## 🚀 Data Pipeline

The project is structured into five sequential stages:

### 01. Data Cleaning & Optimization
*   Loaded raw CSV data from the Instacart dataset.
*   Implemented **Memory Downcasting** to reduce RAM usage by ~60%, enabling local processing of 32 million rows.
*   Separated data into `prior` (history) and `train` (target) sets.

### 02 & 03. Exploratory Data Analysis (EDA)
*   Analyzed user ordering habits (reorder frequency, peak ordering hours, and day-of-week trends).
*   Identified top-performing products and departments.
*   Visualized reorder rates across different categories to inform feature selection.

### 04. Feature Engineering
Constructed a comprehensive feature matrix consisting of:
*   **User Features:** Total orders, average basket size, reorder rate, ordering frequency.
*   **Product Features:** Total times purchased, product reorder rate, add-to-cart position statistics.
*   **User-Product Interaction:** Number of times a specific user bought a specific product, purchase ratio, and recency scores.

### 05. Modeling & Evaluation
*   Implemented a **Candidate-based Recommender System** strategy.
*   Used **Downsampling** (3:1 ratio) to manage class imbalance and optimize performance.
*   Compared three machine learning models:
    *   **Logistic Regression** (Baseline)
    *   **LightGBM** (High Speed)
    *   **XGBoost** (Best Accuracy)

## 📊 Performance Results

| Model | AUC-ROC | F1-Score | Training Time |
| :--- | :---: | :---: | :--- |
| **XGBoost** | **0.8351** | **0.6078** | ~97s |
| **LightGBM** | 0.8228 | 0.5941 | **~16s** |
| Logistic Regression | 0.8072 | 0.5681 | ~569s |

*XGBoost achieved the highest performance, effectively capturing complex user patterns.*

## 🛠 Tech Stack
*   **Language:** Python
*   **Data Processing:** Pandas, NumPy, PyArrow (Parquet)
*   **Machine Learning:** XGBoost, LightGBM, Scikit-Learn
*   **Visualization:** Matplotlib, Seaborn

## ⚙️ Setup & Installation
1.  **Clone the repository:**
    ```bash
    git clone <your-repo-url>
    ```
2.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
3.  **Data Placement:**
    Download the dataset from [Kaggle](https://www.kaggle.com/c/instacart-market-basket-analysis/data) and place the CSV files in `data/raw/`.

4.  **Execution Order:**
    Run the notebooks in numerical order (`01` to `05`).

---
*Created as part of an Advanced Data Science Project.*
