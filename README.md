## End to End Airline Prices Analysis and Prediction Machine learning project - Prathamesh Deshmukhe

### Introduction About the Data :

* The goal is to predict `price` of given airline flight (Regression Analysis). Based on the parameters:
  airline, source_city, departure_time, stops, arrival_time, destination_city, class, days_left before departure date

Target variable:
* `price`: Price of the given airline flight.

Dataset Source Link :
[Airline Flight Prices Data](https://www.kaggle.com/datasets/shubhambathwal/flight-price-prediction?select=Clean_Dataset.csv)


# Approach for the project 

1. Data Ingestion : 
    * In Data Ingestion phase the data is first read as csv. 
    * Then the data is split into training and testing and saved as csv file.

2. Data Transformation : 
    * In this phase a ColumnTransformer Pipeline is created.
    * for Numeric Variables first SimpleImputer is applied with strategy median , then Standard Scaling is performed on numeric data.
    * for Categorical Variables SimpleImputer is applied with most frequent strategy, then ordinal encoding performed , after this data is scaled with Standard Scaler.
    * This preprocessor is saved as pickle file.

3. Model Training : 
    * In this phase base model is tested . The best model found was catboost regressor.
    * After this hyperparameter tuning is performed.
    * This model is saved as pickle file.

4. Prediction Pipeline : 
    * This pipeline converts given data into dataframe and has various functions to load pickle files and predict the final results in python.

5. Flask App creation : 
    * Flask app is created with User Interface to predict the airline flight prices inside a Web Application.

# Exploratory Data Analysis Notebook

Link : [EDA Notebook](https://github.com/Prathamesh3100/Airline_Prices_Analysis_and_Prediction/blob/main/notebook/EDA%20Airline%20Prices.ipynb)

# Model Training Approach Notebook

Link : [Model Training Notebook](https://github.com/Prathamesh3100/Airline_Prices_Analysis_and_Prediction/blob/main/notebook/MODEL%20TRAINING.ipynb)
