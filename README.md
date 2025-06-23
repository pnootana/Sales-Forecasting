# Sales Forecasting Project

An advanced machine learning project aimed at predicting sales for a retail dataset using state-of-the-art regression algorithms. This project involves comprehensive data cleaning, feature engineering, and model optimization techniques to achieve high prediction accuracy.

## Table of Contents

- [Introduction](#introduction)
- [Dataset Overview](#dataset-overview)
- [Data Preprocessing](#data-preprocessing)
- [Feature Engineering](#feature-engineering)
- [Models and Techniques](#models-and-techniques)
- [Model Evaluation](#model-evaluation)
- [Results](#results)
- [Conclusion](#conclusion)
- [Contributing](#contributing)
- [License](#license)

## Introduction

Accurate sales forecasting is crucial for retail businesses to manage inventory, optimize pricing strategies, and maximize profits. This project builds a robust machine learning model to predict sales based on historical data and various product and store attributes.

## Dataset Overview

The dataset used is the **Big Mart Sales** dataset, which contains 8523 rows and 12 variables. It includes information about products across multiple outlets, such as:

- **Item_Identifier**: Unique product ID
- **Item_Weight**: Weight of the product
- **Item_Fat_Content**: Fat content of the product (Low Fat, Regular, etc.)
- **Item_Visibility**: The percentage of total display area allocated to this product in a store
- **Item_Type**: The category to which the product belongs
- **Item_MRP**: Maximum Retail Price (list price) of the product
- **Outlet_Identifier**: Unique store ID
- **Outlet_Establishment_Year**: The year the store was established
- **Outlet_Size**: The size of the store (Small, Medium, High)
- **Outlet_Location_Type**: The type of city in which the store is located
- **Outlet_Type**: Whether the outlet is just a grocery store or some sort of supermarket
- **Item_Outlet_Sales**: Sales of the product in the particular store (Target variable)



## Data Preprocessing

- **Handling Missing Values:**
  - **Item_Weight:** Imputed using **KNNImputer** based on nearest neighbors.
  - **Outlet_Size:** Predicted missing values using a **RandomForestClassifier** trained on other features.

- **Data Cleaning:**
  - Replaced zero values in `Item_Visibility` with the mean visibility.
  - Standardized entries in `Item_Fat_Content`.

- **Feature Encoding:**
  - Applied **One-Hot Encoding** to categorical variables with multiple categories.
  - Used **Label Encoding** for `Outlet_Identifier` and `Item_Type`.

- **Feature Scaling:**
  - Used **StandardScaler** to standardize numerical features.

## Feature Engineering

- **New Features Created:**
  - **Years_Operational:** Number of years the outlet has been operational.
  - **Item_Type_Combined:** Consolidated item types into broader categories.
  - **Price_per_Unit_Weight:** Price of the item per unit weight.
  - **Item_MRP_Tier:** Binned `Item_MRP` into tiers (Low, Medium, High, Very High).

- **Adjusted Features:**
  - Modified `Item_Fat_Content` for non-consumable items.

## Models and Techniques

- **Regression Models Used:**
  - **Linear Regression**
  - **Ridge Regression**
  - **Lasso Regression**
  - **Decision Tree Regressor**
  - **Random Forest Regressor**
  - **ExtraTrees Regressor**
  - **XGBoost Regressor**
  - **LightGBM Regressor**
  - **CatBoost Regressor**

- **Hyperparameter Tuning:**
  - Performed using **GridSearchCV** for `CatBoostRegressor`.

- **Model Evaluation Metrics:**
  - **R2 Score**
  - **Root Mean Squared Error (RMSE)**
  - **Mean Absolute Error (MAE)**

## Model Evaluation

- **Best Model:** `CatBoostRegressor` after hyperparameter tuning.
- **Performance Metrics:**
  - **Train R2 Score:** 0.6041
  - **Test R2 Score:** 0.6211
  - **Train RMSE:** 1076.1006
  - **Test RMSE:** 1040.7172
  - **Train MAE:** 758.3063
  - **Test MAE:** 747.7749

- **Feature Importance:**
  - Analyzed to understand the impact of each feature on the sales prediction.

## Results

- **Residual Analysis:**
  - Performed to ensure that the residuals are normally distributed and to detect any patterns.
  
- **Visualization:**
  - Correlation heatmaps, feature distributions, and residual plots were used to visualize data relationships and model performance.

## Conclusion

The project successfully built a predictive model for sales forecasting with a reasonable accuracy. Advanced data preprocessing and feature engineering significantly improved the model's performance. The `CatBoostRegressor` proved to be the most effective algorithm for this dataset.

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository.
2. Create a new branch:

   ```bash
   git checkout -b feature/your-feature-name
   ```

3. Commit your changes:

   ```bash
   git commit -m "Add your message"
   ```

4. Push to the branch:

   ```bash
   git push origin feature/your-feature-name
   ```

5. Open a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

Feel free to customize this README and GitHub description to better suit your project's specifics or to add any additional information.
