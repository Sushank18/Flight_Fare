
# Flight Fare Prediction

A machine learning regression project that predicts the price of an airline ticket from journey-related features such as airline, source, destination, number of stops, journey date, departure/arrival time, and flight duration.

The project covers an end-to-end machine learning workflow: data cleaning, exploratory data analysis, feature engineering, categorical encoding, outlier analysis, model training, hyperparameter tuning, evaluation, and model serialization.

## Project Overview

The dataset contains 10,683 flight records and 11 columns in the original training data. After handling missing values, 10,462 records are used for feature engineering and modeling.

The target variable is:

- **Price** — predicted flight fare

**Important input features include:**

- Airline
- Date of Journey
- Source
- Destination
- Total Stops
- Departure Time
- Arrival Time
- Duration
- Additional Information

## Workflow

1. **Data Cleaning**

- Loaded the training dataset from Excel.
- Checked data types and missing values.
- Removed rows containing missing values.
- Examined duplicate records.

2. **Feature Engineering**

The notebook transforms raw flight information into machine-learning-friendly features:

- Extracted journey day, month, and year from the journey date.
- Extracted hour and minute from departure and arrival times.
- Converted flight duration into hours and minutes.
- Created total duration in minutes.
- Converted categorical variables into numerical representations.
- Applied one-hot encoding to the Source feature.
- Used target-guided ordering for categorical variables such as Airline.

3. **Exploratory Data Analysis**

The project analyzes relationships between flight characteristics and ticket prices using visualizations such as:

- Distribution plots
- Box plots
- Bar charts
- Category-wise price comparisons
- Feature importance analysis

4. **Model Development**

The processed data is divided into training and testing sets using a **75:25** split with random_state=42.
A **RandomForestRegressor** is trained to predict flight fares.

5. **Hyperparameter Tuning**

RandomizedSearchCV with **4-fold cross-validation** is used to tune the Random Forest hyperparameters.

The best configuration recorded in the notebook is:

- n_estimators = 980
- min_samples_split = 10
- max_features = None
- max_depth = 20

6. **Model Evaluation**

The recorded test-set results are:

- R² Score : 0.8388
- Mean Absolute Error (MAE) : 1127.63
- Mean Absolute Percentage Error (MAPE) : 13.07%

These values are from the executed notebook cells in the repository and may change if the data, preprocessing, random state, or model configuration is changed.

## Feature Importance

The Random Forest analysis in the notebook shows the following features among the strongest contributors:

Feature : Importance

- Total Stops : 0.4479
- Airline : 0.1712
- Journey Day : 0.1114
- Journey Month : 0.0724
- Duration Hour : 0.0319

**Total_Stops** is the most important feature in the recorded feature-importance output.


## Technologies Used

- Python
- Pandas — data manipulation
- NumPy — numerical operations
- Matplotlib — visualization
- Seaborn — statistical visualization
- Plotly — interactive visualization
- Scikit-learn — preprocessing, modeling, evaluation, and hyperparameter tuning
- OpenPyXL — Excel file handling
- Pickle — model serialization
- Jupyter Notebook — development and analysis


## Model

The final model is a **Random Forest Regressor**, selected and tuned for the flight-fare regression task.
The trained model is serialized using Pickle and stored as:
- rd_random.pkl

The notebook also demonstrates loading the serialized model and generating predictions on the test split.

## Results

The final recorded model achieves an **R² score** of approximately **0.8388** on the held-out test data, with an **MAE** of approximately **1127.63** and **MAPE** of approximately **13.07%**.

The project therefore demonstrates a complete practical regression workflow from raw flight data to a trained and serialized machine learning model.


### Author

- Sushank Yadav
- GitHub: @Sushank18

### License

- This project is available for educational and portfolio purposes.
