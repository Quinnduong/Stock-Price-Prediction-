This project aims to predict the daily price direction of Tesla, Inc. (TSLA) stock, utilizing various machine learning models and time-series data. The objective is not to predict the exact price but to determine whether the next day's closing price will be higher or lower than the opening price (a binary classification problem). The project covers data exploration, feature engineering, model training, and evaluation across various classical and deep learning algorithms.

Project Overview

## Objective:

Predict if Tesla's stock closing price will be higher or lower than the opening price for the next day.
Use historical data from 2010-2024, split into training (2010-2020), validation (2020-2022), and testing (2022-2024) sets.

Data:

### Data source: Daily historical stock prices for Tesla from 2010 to 2024.

Files:

TSLA_train.csv (2010-2020)
TSLA_val.csv (2020-2022)
TSLA_test.csv (2022-2024)

Features: Date, Open, High, Low, Close, Adjusted Close, Volume.

## Data Exploration

The initial exploration revealed that the dataset consists of 2519 rows and 7 columns with no missing values. Key statistics (mean, min, max) were calculated to understand the stock's trends over time.

Visualizations:
Stock Price Time Series: A plot of Open, Close, High, and Low prices over time (TSLA_test.csv).

<img width="764" alt="Screenshot 2024-09-25 at 1 23 05 PM" src="https://github.com/user-attachments/assets/3a8128de-2385-4286-8420-ba8b94e78dcd">

## Feature Engineering

To better predict stock price movements, the following features were engineered:

Target Variable: Created a binary target indicating if the closing price is higher than the opening price.

Moving Averages: Calculated 3-day and 7-day moving averages to capture stock price trends.

Lag Features: Added features like prior day’s prices to account for stock market momentum.

## Model Training and Evaluation

Several machine learning models were applied to predict the target variable:

### Classical Machine Learning Models:
Logistic Regression: Baseline model, but underperformed with an AUC below 0.5.

<img width="775" alt="Screenshot 2024-09-25 at 1 25 43 PM" src="https://github.com/user-attachments/assets/3928644d-77d9-459a-8e54-df92b25af099">

Decision Tree: Showed a slight improvement but still underperformed

<img width="766" alt="Screenshot 2024-09-25 at 1 26 17 PM" src="https://github.com/user-attachments/assets/4a190b1b-8423-48e7-8938-396f5708bbb0">

Random Forest: Best performer among classical models with an AUC of 0.52 on validation data.

<img width="752" alt="Screenshot 2024-09-25 at 1 28 24 PM" src="https://github.com/user-attachments/assets/5f67dbe2-a6ca-4f9d-9627-86b6e8968c7d">

Gradient Boosting: Performed similarly to logistic regression.

<img width="773" alt="Screenshot 2024-09-25 at 1 27 48 PM" src="https://github.com/user-attachments/assets/34f4933d-4f6b-4119-b650-78915d5cd838">

Deep Learning:

Implemented a small neural network using TensorFlow and Keras. Despite extensive tuning, it failed to outperform the random forest model, with an AUC near 0.5.

Results:

Best Model: Random Forest performed the best, with the highest AUC score of 0.52 on the validation set.

Feature Importance: A feature importance plot was generated, showing which stock attributes (like Open, Close, Moving Averages) were most predictive of the target variable.

<img width="766" alt="Screenshot 2024-09-25 at 1 31 27 PM" src="https://github.com/user-attachments/assets/be9b9d94-5918-4953-a11a-c35ce47b330e">
