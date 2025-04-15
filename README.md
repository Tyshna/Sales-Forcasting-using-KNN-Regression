# Sales Forecasting

## Overview

The code aims to forecast product sales based on advertising budgets across different media (TV, Radio, and Newspaper). The analysis uses a dataset containing advertising spending and corresponding sales figures to build a predictive model. The goal is to understand the relationship between advertising expenditure and sales to help in budget planning.

## Dataset Description

The dataset includes the following attributes:

- **TV:** TV advertising budget (in thousands of dollars).
- **Radio:** Radio advertising budget (in thousands of dollars).
- **Newspaper:** Newspaper advertising budget (in thousands of dollars).
- **Sales:** Product sales (in thousands of dollars).

## Code Description

1. **Import Libraries:**
    - pandas is used for data manipulation and analysis.
    - numpy is used for numerical operations.
    - matplotlib.pyplot is used for data visualization.
    - seaborn is used for enhanced data visualization.
2. **Load Dataset:**
    - The dataset is loaded from a CSV file into a pandas DataFrame.
3. **Data Inspection:**
    - The first few rows of the DataFrame are printed to display the data structure.
    - The code checks for missing values in the dataset and prints the sum of null values for each column.
4. **Feature and Target Variable Separation:**
    - The dataset is split into independent features (TV, Radio, Newspaper) and the dependent target variable (Sales).
    - The feature DataFrame (features_df) contains the advertising budgets.
    - The target DataFrame (target_df) contains the sales figures.
5. **Feature Scaling:**
    - The feature variables are normalized using StandardScaler to ensure they have a mean of 0 and a standard deviation of 1. This is important for algorithms like KNeighborsRegressor, which are sensitive to the scale of the input features.
    - The scaled features are converted into a DataFrame (scaled_features).
6. **Train-Test Split:**
    - The dataset is split into training and testing sets using train_test_split.
    - The training set is used to train the KNeighborsRegressor model, and the testing set is used to evaluate its performance.
    - 33% of the data is used for testing (test_size=.33), and random_state=42 ensures reproducibility of the split.
7. **Model Training and Evaluation:**
    - A KNeighborsRegressor model is used to predict sales.
    - The code iterates through different values of n_neighbors (from 1 to 20) to evaluate the model's performance with varying numbers of neighbors.
    - For each n_neighbors value, the model is trained on the training data, and the accuracy scores (R^2) are calculated for both the training and testing sets.
    - The accuracy scores are stored in the acc_train and acc_test lists.
8. **Visualization of Results:**
    - A line plot is generated to visualize the training and testing accuracy scores as a function of the number of neighbors (k).
    - This plot helps in selecting an optimal value for n_neighbors by showing how the model's performance changes with different k values.
9. **Final Model Training and Evaluation:**
    - A KNeighborsRegressor model is trained with n_neighbors=2.
    - The accuracy scores (R^2) are calculated and printed for both the training and testing sets, providing an evaluation of the model's performance.
