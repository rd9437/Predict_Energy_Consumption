# Power Consumption Prediction using Random Forest

This project involves building a predictive model to estimate power consumption using a **Random Forest Regressor**. The goal is to analyze historical data, train a model, and evaluate its performance for predicting future power consumption.

## Project Overview
The dataset contains daily power consumption data, and the objective is to predict future power consumption based on various features such as:
- Date of the measurement
- Day of the week
- Month
- Semester
- Quarter

We use **Random Forest Regressor** to predict power consumption, evaluate the model performance using **Mean Absolute Error (MAE)** and **Root Mean Squared Error (RMSE)**, and visualize the actual vs predicted power consumption.

## Data

The project uses two CSV files for training and testing:

1. **df_train.csv** - Training data containing historical power consumption records.
2. **df_test.csv** - Test data used to evaluate the model’s performance.

### Columns:

Available in `df_train.csv` and `df_test.csv`:

| Column             | Type   | Description                                                                 |
|--------------------|--------|----------------------------------------------------------------------------|
| date               | chr    | Date of the measurement                                                    |
| power_consumption  | dbl    | Daily power consumption (in kilowatts)                                     |
| year               | int    | Year of the measurement                                                    |
| semester           | int    | Semester of the measurement (1 for Jan-Jun, 2 for Jul-Dec)                 |
| quarter            | int    | Quarter of the measurement (1 for Q1, 2 for Q2, 3 for Q3, 4 for Q4)        |
| day_in_week        | chr    | Day of the week of the measurement (e.g., Monday, Tuesday)                 |
| week_in_year       | int    | Week number in the year of the measurement                                 |
| day_in_year        | int    | Day number in the year of the measurement                                  |
| month              | int    | Month of the year of the measurement 

## Model
The model used for predicting power consumption is the **Random Forest Regressor** from `sklearn.ensemble`. Random Forest is an ensemble learning method that builds multiple decision trees and aggregates their predictions. It is widely used for regression tasks and can handle complex non-linear relationships in data.

### Steps Involved:
1. **Data Preprocessing**:
   - One-hot encoding for `day_in_week` to convert categorical variables into numerical format.
   - Ensuring that the test data has the same features as the training data.

2. **Training**:
   - Splitting the data chronologically into training and validation sets (80% train, 20% validation).
   - Training the Random Forest model on the training set.

3. **Evaluation**:
   - Predicting power consumption on the validation set.
   - Calculating **MAE** and **RMSE** to evaluate the model's performance.
   - Plotting **actual vs predicted power consumption** for validation and test sets.

4. **Test Prediction**:
   - The model is then used to predict power consumption on the test set and evaluate the results.

## Setup
To run the project on your local machine, follow these steps:

### Prerequisites:
Ensure you have the following installed:
- Python 3.x
- pip (Python package installer)

### Installation:
1. Clone the repository:
   ```
   git clone https://github.com/rd9437/predict_energy_consumption.git
   cd predict_energy_consumption 
   ```
