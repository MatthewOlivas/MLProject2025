# MLProject2025
# Model#4 Gradiant Boosted Tree
# Vehicle Price Prediction

This project uses Craigslist vehicle listings to predict used car prices based on various features like age, odometer reading, condition, transmission type, and title status. The models we built are KNN, Decision Tree, Linear Regression, and Gradiant Boosted tree. The dataset is loaded directly from Kaggle using `kagglehub`.

## File: `XGBoosted.ipynb`
## How to run:
Press the start button when you load into google colab for each of the files.

### What This Script Does:

1. **Loads Data**
   - Loads `vehicles.csv` from the "austinreese/craigslist-carstrucks-data" Kaggle dataset using `kagglehub`.

2. **Cleans and Prepares Data**
   - Drops irrelevant columns.
   - Filters unrealistic price and year values.
   - Adds a new column `age` from the vehicle's manufacturing year.
   - One-hot encodes categorical variables.

3. **Splits and Scales Data**
   - Splits data into training and testing sets.
   - Normalizes the `odometer` column using `StandardScaler`.

4. **Trains a Model**
   - Trains an `XGBRegressor` on the training data.

5. **Evaluates Performance**
   - Calculates metrics such as MAE, RMSE, R², MAPE, and more.
   - Displays a performance table using `tabulate`.

6. **Visualizations**
   - Bar plot of the top 20 most important features (using permutation importance).
   - Scatter plot comparing actual vs. predicted prices.
   - Histogram showing the distribution of vehicle ages.

7. **Predicts a Sample Input**
   - Makes a prediction for a predefined vehicle input (e.g., a 5-year-old sedan in good condition).

## Dependencies

You can install all necessary packages with:

```bash
pip install pandas numpy matplotlib seaborn scikit-learn xgboost kagglehub tabulate
