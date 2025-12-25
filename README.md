# Diamond Data Analysis

## Overview
This project explores a diamond dataset to understand how diamond characteristics (carat, cut, color, clarity, depth, table, and physical dimensions) relate to **price**. The notebook walks through data loading, cleaning, feature engineering (adaptation), visualization, correlation analysis, and linear regression modeling.

## Objectives
- Explore the diamond dataset structure and basic statistics
- Clean the data (handle missing values)
- Engineer additional features:
  - **Volume** (approx.) from dimensions
  - **Price per carat**
- Visualize relationships between key variables
- Analyze correlations between numeric features
- Build:
  - **Simple Linear Regression**
  - **Multiple Linear Regression**

## Dataset
**File:** `diamonds1.csv`  
**Rows / Columns:** 53,940 rows × 11 columns

### Key Columns
- `carat` — diamond weight
- `cut` — quality of the cut (categorical)
- `color` — diamond color grade (categorical)
- `clarity` — diamond clarity grade (categorical)
- `depth` — total depth percentage
- `table` — width of top of diamond relative to widest point
- `price` — price in USD
- `length(mm (0--10.74))` — length in mm
- `width( mm (0--58.9))` — width in mm
- `depth(mm 0--31.8)` — depth in mm
- `Unnamed: 0` — index-like column (not a feature)

## Project Workflow
1. **Data Exploration**
   - View column names, dataset shape, and a quick preview (`glimpse`, `dim`).
2. **Data Cleaning**
   - Remove missing values using `drop_na()` (tidyr).
3. **Adaptation (Feature Engineering)**
   - Create:
     - `volume_df` ≈ `length * width * depth`
     - `Price_per_Carat` = `price / carat`
   - Combine into `Adapation_data`.
4. **Descriptive Visualization**
   - Scatter plots and bar plots using `ggplot2`
   - Example comparisons: depth vs table, carat vs color, price_per_carat vs clarity, etc.
5. **Correlation Analysis**
   - Correlation matrix on numeric columns
   - Heatmap using `corrplot`
6. **Regression Modeling**
   - Simple Linear Regression
   - Multiple Linear Regression
   - Diagnostic plots for regression assumptions (residual plots, Q-Q plots)

## Tools & Libraries
The notebook is written in **R** (inside a `.ipynb` notebook) and uses:
- `dplyr`
- `tidyverse`
- `tidyr`
- `ggplot2`
- `corrplot`

## How to Run
### Option A: Run in Jupyter Notebook (R kernel)
1. Open `Diamond_Project.ipynb`.
2. Ensure an R kernel is available (e.g., IRkernel).
3. Place `diamonds1.csv` in the expected path.
4. Run cells top-to-bottom.

### Option B: Run in Google Colab
1. Upload `Diamond_Project.ipynb` and `diamonds1.csv`.
2. Update the dataset path if needed (example in notebook uses):
   ```r
   diamond_data <- read.csv("/content/diamonds1.csv")
