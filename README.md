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
Description:
This advanced Python script includes a more complex machine learning project, likely involving multiple models and techniques such as hyperparameter tuning or model ensembling. It might also implement cross-validation and feature scaling, aiming for higher performance in predictive accuracy. This script represents a culmination of the methods learned, combining them into a more refined and optimized model.

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


