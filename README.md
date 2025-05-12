# 🚗 Used Car Price Prediction

This project predicts used car prices based on various features scraped from listings. The dataset was cleaned, engineered, and used to train and evaluate four different machine learning models.

---

## Data Preprocessing

- Dropped irrelevant columns like `lat`, `long`, `posting_date`, etc.
- Removed rows with invalid or extreme `price` and `year` values.
- Added a new `age` column derived from the year of the car.
- Filled missing numeric values with the **mean**.
- Filled missing categorical values with **'alternatives'**.
- Grouped rare categories into **'uncommon'** to reduce dimensionality.
- Used **one-hot encoding** for categorical features.
- Scaled numeric features (`age` and `odometer`) using **StandardScaler**.

---

## Our Models Trained

### 1. ** Decision Tree **
- Trained on full preprocessed data.
- Evaluated using MAE, MSE, RMSE, and R² score.
- Offers built-in feature importance analysis.
- Great balance of performance and interpretability.

### 2. ** KNN **
- Sequentially builds an ensemble of weak learners.
- Generally offers better performance than Random Forest.
- More sensitive to parameter tuning and overfitting.

### 3. ** Gradient Boosted Tree Regressor **
- High-performance version of Gradient Boosting.
- Efficient, fast, and handles regularization well.
- Typically outperforms the other models in accuracy.
- Useful for Kaggle-style competitive modeling.

### 4. ** Linear Regression **
- Simple and interpretable baseline.
- Trained in two versions:
  - **Full feature set**
  - **Top 10 features** based on **permutation importance**
- Helps understand the linear relationship between features and price.
- Not as accurate as tree-based models, but excellent for feature insight.

---

## Evaluation Metrics

Each model was evaluated using:

- **MAE** (Mean Absolute Error)
- **MSE** (Mean Squared Error)
- **RMSE** (Root Mean Squared Error)
- **R² Score**

Example (from Linear Regression):
```
MAE: 2889.73  
MSE: 18322137.34  
RMSE: 4280.44  
R² Score: 0.65
```

---

## Feature Importance

We used **permutation importance** and **built-in feature importances** to rank the most valuable predictors of price. Common top features across models include:

- `age`
- `odometer`
- `model`
- `manufacturer`
- `condition`
- `drive`

---

## Conclusion

- **XGBoost** offered the best accuracy overall.
- **KNN** gave solid results with good feature importance.
- **Decision Tree** was close behind XGBoost in accuracy.
- **Linear Regression** was simple but offered valuable feature insights.
- Reducing to the **top 10 features** made Linear Regression more efficient with minimal performance drop.

---
