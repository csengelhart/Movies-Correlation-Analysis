# 🎬 Movie Gross Revenue Analysis

This repository contains a Jupyter Notebook that performs an **Exploratory Data Analysis (EDA)** on a movie dataset to understand the factors influencing a movie's **gross revenue**.

---

## 🎯 Project Goal

The primary objective of this analysis is to identify **key variables** that exhibit a strong correlation with a movie's gross revenue, providing insights into what might contribute to a film's **financial success**.

---

## 📂 Dataset

The analysis uses a dataset named `movies.csv`, which contains various attributes about movies, including:

- `name`
- `rating`
- `genre`
- `year`
- `released`
- `score`
- `votes`
- `director`
- `writer`
- `star`
- `country`
- `budget`
- `gross`
- `company`
- `runtime`

---

## 🛠️ Tools Used

- **Python**: Core programming language.
- **Jupyter Notebook**: For interactive analysis and visualization.
- **Pandas**: For data manipulation and analysis.
- **NumPy**: For numerical operations.
- **Matplotlib**: For basic plotting.
- **Seaborn**: For advanced statistical visualizations.

---

## 🧪 Analysis Steps

### 1. Data Loading and Initial Inspection
- Loaded `movies.csv` into a Pandas DataFrame.
- Inspected the first few rows to understand structure and content.

### 2. Missing Data Handling
- Checked for missing values across all columns.
- Dropped rows with any missing values (especially in `budget` and `gross`).
- Reconfirmed dataset integrity post-cleaning.

### 3. Data Type Conversion
- Converted `budget` and `gross` from `float` to `int64` for consistent numerical representation.

### 4. Feature Engineering: `yearcorrect`
- Identified discrepancies between `year` and `released`.
- Created `yearcorrect` by extracting a 4-digit year from the `released` column using regex.

### 5. Data Cleaning and Preparation
- Sorted DataFrame in descending order of `gross` revenue.
- Removed duplicate rows to maintain data quality.

### 6. Correlation Analysis
#### Initial Numeric Correlation:
- Generated a correlation matrix.
- Key findings:
  - `budget`: **0.74**
  - `votes`: **0.61**

#### Visualizing Numeric Correlations:
- Created scatter plots:
  - `budget` vs `gross`
  - `votes` vs `gross`
- Added regression lines using `Seaborn`'s `regplot`.
- Plotted a heatmap for numeric correlation matrix.

### 7. Categorical to Numeric Conversion (for full correlation matrix)
- Created `df_numerized`, a deep copy of the original DataFrame.
- Converted all `object` columns to `category` and then encoded using `cat.codes`.
- Generated a full correlation heatmap including encoded categorical features.

### 8. Unstacking and Filtering Correlations
- Unstacked and sorted correlation matrix.
- Highlighted strongest correlations:
  - `budget` and `gross`
  - `votes` and `gross`

---

## 📌 Key Findings

- **Budget** has a strong positive correlation (**0.74**) with **Gross Revenue**.
- **Votes** also has a strong positive correlation (**0.61**) with **Gross Revenue**.

These findings suggest that:
- Higher budgets are generally linked to higher gross earnings.
- More votes (indicating popularity or engagement) are often tied to higher financial success.

---

## ▶️ How to Run the Analysis

1. **Clone the repository**:
    ```bash
    git clone <repository_url>
    ```

2. **Navigate to the project directory**:
    ```bash
    cd Movie-Gross-Revenue-Analysis
    ```

3. **Install the required libraries**:
    ```bash
    pip install pandas numpy matplotlib seaborn
    ```

4. **Prepare your dataset**:
    - Place `movies.csv` in the following directory:
      ```
      Dataset/movies.csv
      ```
    - *(Update the notebook path if needed)*

5. **Launch the Jupyter Notebook**:
    ```bash
    jupyter notebook Movie_Analysis.ipynb
    ```

6. **Run all cells** to reproduce the analysis and visualizations.


