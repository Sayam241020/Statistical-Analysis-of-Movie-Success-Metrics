# 🎬 Statistical Analysis of Movie Success Metrics

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Libraries](https://img.shields.io/badge/Library-SciPy%20%7C%20Statsmodels%20%7C%20Pandas-orange)
![Status](https://img.shields.io/badge/Status-Completed-green)

## 📌 Project Overview
This project performs a rigorous statistical analysis on the **TMDB 5000 Movie Dataset** (4,800+ movies) to determine the factors that drive commercial success and audience engagement.

Unlike standard EDA, this project focuses on **Hypothesis Testing** (T-tests, ANOVA, F-tests) to validate strategic questions regarding release timing, director impact, and budget efficiency.

## 📂 Dataset
* **Source:** [TMDB 5000 Movie Dataset](https://www.kaggle.com/datasets/tmdb/tmdb-movie-metadata)
* **Scale:** 4,803 Movies, 20+ Features.
* **Data Structure:** Contains complex nested JSON objects for `crew`, `cast`, and `production_companies` which required extensive preprocessing.

## 🔍 Key Hypotheses Tested
We formulated and tested **9 specific hypotheses**, including:
1.  **Normality:** Are numerical features (Budget, Revenue) normally distributed?
2.  **Cast Size:** Do movies with larger casts achieve higher popularity scores?
3.  **Budget Efficiency:** Do high-budget movies have a better revenue-to-budget ratio?
4.  **Release Timing:** Do Weekend releases garner more engagement (votes/minute) than Weekday releases?
5.  **Director Analysis:** Does **Christopher Nolan** show higher consistency (lower variance) in popularity compared to the average?
6.  **Franchise Success:** Do sequels consistently out-earn original installments?
7.  **Star Power:** Does Leonardo DiCaprio perform statistically better in Action vs. Drama?

## 🛠 Technical Implementation

### 1. Data Engineering & Cleaning
* **JSON Parsing:** Utilized `json` and `pandas` to flatten nested list-of-dictionary structures in `cast` and `crew` columns to extract Director names and Cast sizes.
* **Feature Engineering:** Created custom metrics such as `ROI` (Return on Investment) and `Votes_Per_Runtime_Minute` to normalize engagement metrics.

### 2. Statistical Methods
* **Shapiro-Wilk Test:** To check for normality distributions.
* **Levene’s Test / F-Test:** To analyze variance (specifically for the Christopher Nolan consistency hypothesis).
* **Independent T-Tests:** To compare means between two groups (e.g., Weekday vs. Weekend).
* **One-Way ANOVA:** For comparing means across multiple groups (e.g., Cast Size buckets).

## 📊 Key Insights & Results

| Hypothesis | Test Used | Outcome | Insight |
| :--- | :--- | :--- | :--- |
| **Weekday vs Weekend** | T-Test | **Significant** | Surprisingly, **Weekday releases** showed higher vote-counts-per-minute than Weekend releases. |
| **Nolan vs Others** | F-Test (Variance) | **Significant** | Christopher Nolan's movies have **higher variance** in popularity, suggesting "high risk, high reward" reception compared to the industry average. |
| **Feature Distribution** | Shapiro-Wilk | **Rejected** | Key financial metrics (Budget, Revenue) do **not** follow a normal distribution, necessitating non-parametric approaches or log-transformations for future modeling. |

*(Note: Several other hypotheses, such as seasonality effects, showed no statistically significant differences in this specific dataset.)*

## 🚀 How to Run
1.  **Clone the repository**
    ```bash
    git clone [https://github.com/Sayam241020/Movie-Success-Analysis.git](https://github.com/Sayam241020/Movie-Success-Analysis.git)
    ```
2.  **Install dependencies**
    ```bash
    pip install pandas numpy matplotlib scipy statsmodels
    ```
3.  **Run the Notebook**
    ```bash
    jupyter notebook "brsm_final_projec_code.ipynb"
    ```

## 📈 Future Work
* **Multivariate Regression:** Build a prediction model for Revenue using the significant features identified.
* **NLP Analysis:** Perform sentiment analysis on movie overviews/taglines to correlate with popularity.
* **Crew Diversity:** Analyze if crew role diversity correlates with critical acclaim.

---
**
