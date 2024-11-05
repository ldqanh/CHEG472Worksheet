# CHEG472Worksheet
Week 1
Description:
This Jupyter notebook contains introductory-level data analysis. It covers fundamental data science techniques, such as data loading, basic exploratory data analysis (EDA), and data visualization. The primary focus is on getting familiar with Python libraries like Pandas, Matplotlib, and Seaborn to analyze data distributions and visual patterns.

Week 2
Description:
This second notebook builds on the basics and dives deeper into data preprocessing and feature engineering. It introduces techniques for handling missing values, data transformation, and encoding categorical variables. Additional EDA steps provide a deeper understanding of the data and prepare it for more advanced model training tasks.

Week 3
This Python script processes and analyzes a dataset containing chemical composition and related parameters. It focuses on identifying and handling outliers, generating summary statistics, and visualizing data distributions. Key Steps:
- Z-score Calculation:
   - Computes Z-scores for mole fractions of CO, H2, and CO2 to identify potential outliers.
- Outlier Detection:
   - Outliers are identified based on Z-scores exceeding ±3.
   - The script drops identified outliers from the dataset.
- Outlier Handling:
   - Capping: Values exceeding a defined threshold (0.5) for mole fractions are capped.
   - Imputation: Missing values resulting from capping are replaced with the mean of their respective columns.
- Summary Statistics:
   - Calculates summary statistics (mean, count, min, max, etc.) for C/H and O/H ratios, as well as temperature statistics, grouped by feed type.
- Visualization:
   - Generates box plots and histograms for:
      - Temperature
      - Carbon content
      - Hydrogen selectivity
      - CO and H2 mole fractions
      - CO2 mole fraction
   - Analyzes distributions and trends to identify relationships in the data.
- Target and Feature Selection:
   - Defines target variables related to mole fractions and hydrogen selectivity.
   - Separates features for model training by excluding non-relevant columns.

Week 4
This script performs exploratory data analysis (EDA) on a dataset concerning various chemical components, focusing on data cleaning, outlier detection, correlation analysis, and visualization techniques. Key Steps:
- Data Loading and Initial Exploration: The dataset is loaded from an Excel file.
   - Displays the first few rows, the dataset's columns, and checks the data types to identify numeric columns.
   - Checks for missing data, confirming that there are no missing values.
- Box Plot Analysis:
   - Box plots for each numeric column (C, H, N, O, S, VM) are generated to visually assess the presence of outliers. Initial analysis shows no outliers in the C (%) column.
- Outlier Detection Using IQR:
   - The Interquartile Range (IQR) method is applied to identify and filter out outliers across all numeric columns.
   - A box plot is created to visualize the remaining data without outliers.
- Descriptive Statistics:
   - Summary statistics are calculated for the data without outliers, including mean, median, standard deviation, minimum, maximum, and IQR, highlighting key characteristics of the dataset.
- Data Encoding:
   - Categorical variables are identified and transformed using one-hot encoding to facilitate further analysis.
   - Checks for duplicate columns in the encoded data, confirming none are present.
- Correlation Analysis:
   - A correlation matrix is computed for the numeric columns in the dataset without outliers.
   - A heatmap visualization of the correlation matrix is generated, revealing significant relationships, such as a strong positive correlation between Ash (%) and N (%) and a perfect correlation between Cellulose (Cel) and Hemicellulose (Hem).
- Visualization of Relationships:
   - Scatter plots and count plots are created for specific relationships and categorical variables (e.g., C (%) vs. H (%), counts by Location).
   - Pair plots for multiple numeric variables are generated to visualize relationships among them.
- Principal Component Analysis (PCA):
   - PCA is applied to the scaled numeric data to reduce multicollinearity and retain significant variance.
   - The explained variance of each principal component is evaluated, and the optimal number of components is determined to retain 95% cumulative variance.
- Final Insights:
   - The analysis concludes that while C and O exhibit strong correlations, the correlation between MSP and other variables is minimal.
   - Outliers have been effectively addressed by removing affected data points, allowing for a clearer understanding of the dataset's structure.

Week 5:
# Feature Selection and Model Training Script

This Python script is designed for feature selection, preprocessing, and training various regression models to predict the market selling price (`MSP`) based on input features related to chemical composition and plant capacity.

## Overview

1. **Data Preparation:**
   - The script selects relevant features, including chemical percentages (`H (%)`, `N (%)`, `O (%)`, `VM (%)`, `Ash (%)`, `Cel (%)`, `Hem (%)`) and `Plant capacity (kg/hr)`.
   - The dataset is split into training (80%) and testing (20%) sets.

2. **Preprocessing:**
   - Numerical features undergo log and polynomial transformations.
   - Categorical features are one-hot encoded to facilitate model training.

3. **Model Training:**
   - Several regression models are initialized and evaluated, including:
     - **Linear Models:** Linear Regression, SGD Regressor
     - **Tree-based Models:** Random Forest, Extra Trees, Gradient Boosting, AdaBoost
     - **Support Vector Regression:** SVR
     - **Neural Networks:** Multi-layer Perceptron (MLP)
     - **Ensemble Methods:** Stacking Regressor combining multiple models.
   - Models are evaluated based on R² Score, Mean Squared Error (MSE), and Mean Absolute Error (MAE).

4. **Model Selection:**
   - Models with an R² score greater than 0.95 are retained for further evaluation.

5. **Visualization:**
   - The script includes functions to visualize feature importance using bar plots and interpret model predictions using SHAP values.

6. **Model Persistence:**
   - The best performing model is saved for future use, allowing for easy deployment in a production environment.

## Example Usage

Load your dataset into a Pandas DataFrame named `data`, and run the `train_evaluate_stacking_model(data)` function to initiate the training and evaluation process. Visualizations can be generated using the provided plotting functions.

## Conclusion

This script serves as a comprehensive framework for preprocessing data, training multiple regression models, and evaluating their performance, providing a solid foundation for predictive analytics tasks in chemical engineering contexts.


