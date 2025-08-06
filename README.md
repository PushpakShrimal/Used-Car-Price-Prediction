# Used-Car-Price-Prediction
🚗 A machine learning model that predicts used car prices using a Random Forest Regressor. Includes feature engineering, hyperparameter tuning, and model deployment.


# 🚗 Used Car Price Prediction

![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg?logo=python&logoColor=white)
![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-0.24%2B-orange?logo=scikit-learn)
![Pandas](https://img.shields.io/badge/Pandas-1.3%2B-150458?logo=pandas)
![Seaborn](https://img.shields.io/badge/Seaborn-0.11%2B-150458?logo=seaborn)
![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

---

## 🎯 Project Goal

The goal of this project is to build a regression model that accurately predicts the selling price of used cars. This model can be a valuable tool for both car sellers to estimate a fair market value and for buyers to verify they are getting a good deal.

## 📊 Dataset

The dataset used for this project is `car data.csv`, which contains information about used cars sold in India. The key features include:

-   `Present_Price`: The current showroom price of the car (in Lakhs).
-   `Kms_Driven`: The total kilometers the car has been driven.
-   `Fuel_Type`: The type of fuel the car uses (Petrol, Diesel, CNG).
-   `Seller_Type`: Whether the seller is a Dealer or an Individual.
-   `Transmission`: The car's transmission type (Manual, Automatic).
-   `Owner`: The number of previous owners.
-   `no_of_year`: The age of the car, engineered from the manufacturing year.

## 🛠️ Project Workflow

This project follows a structured data science workflow from data exploration to model deployment:

1.  **Data Exploration & Preprocessing:** The dataset was loaded and checked for null values and inconsistencies.
2.  **Feature Engineering:** A new feature, `no_of_year`, was created by subtracting the manufacturing `Year` from the current year to represent the car's age, which is more intuitive for a regression model.
3.  **Encoding Categorical Data:** Categorical features like `Fuel_Type`, `Seller_Type`, and `Transmission` were converted into numerical format using one-hot encoding.
4.  **Feature Importance Analysis:** An `ExtraTreesRegressor` was used to identify the most significant features for predicting the selling price. The analysis revealed that `Present_Price` is the most influential factor.
5.  **Model Training:** A **Random Forest Regressor** was selected for its robustness and high performance in regression tasks.
6.  **Hyperparameter Tuning:** `RandomizedSearchCV` was employed to perform an exhaustive search for the optimal hyperparameters, significantly improving the model's predictive accuracy.
7.  **Model Evaluation:** The final model's predictions were compared against the actual test set values, showing a close alignment and strong performance.
8.  **Model Deployment:** The trained model was serialized and saved into a `random_forest_regressor_model.pkl` file, making it ready for deployment in a web application or other production environments.

## 💡 Key Insights

### Feature Importance

The analysis of feature importance confirmed that the **current market price (`Present_Price`) of a car is the single most important factor** in determining its resale value. The age of the car (`no_of_year`) and whether it's a manual or automatic (`Transmission_Manual`) also play significant roles.

*(You can add a screenshot of your Feature Importance chart here)*

### Correlation Analysis

A heatmap of feature correlations showed a strong positive correlation between `Present_Price` and `Selling_Price`, which is expected and validates the data's quality.

*(You can add a screenshot of your Correlation Heatmap here)*

## 🏆 Model Performance

After hyperparameter tuning, the Random Forest Regressor performed exceptionally well. The distribution plot below shows a strong overlap between the actual values and the model's predictions on the test data, indicating high accuracy.

*(You can add a screenshot of your Actual vs. Predicted distribution plot here)*

## 🚀 How to Run this Project

1.  **Clone the repository:**
    ```bash
    git clone [https://github.com/PushpakShrimal/Used-Car-Price-Prediction.git](https://github.com/PushpakShrimal/Used-Car-Price-Prediction.git)
    cd Used-Car-Price-Prediction
    ```
2.  **Create and activate a virtual environment:**
    ```bash
    python -m venv env
    source env/bin/activate  # On Windows: env\Scripts\activate
    ```
3.  **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
4.  **Run the Jupyter Notebook:**
    ```bash
    jupyter notebook notebooks/"Project_3(Predicting_Used_Car_Prices) (1).ipynb"
    ```

---
