## End to End Airline Prices Analysis and Prediction Machine learning project - Prathamesh Deshmukhe

### Introduction About the Data :

**The dataset** The goal is to predict `price` of given airline flight (Regression Analysis).
airline             0
source_city         0
departure_time      0
stops               0
arrival_time        0
destination_city    0
class               0
days_left           0
price               0
dtype: int64

**There are 8 independent variables :
1. airline: The airline carrier of the flight. Categories include:

* SpiceJet
* AirAsia
* Vistara
* GO_FIRST
* Indigo
* Air_India

2. source_city: The city from which the flight departs. Categories include:

* Delhi
* Mumbai
* Bangalore
* Kolkata
* Hyderabad
* Chennai

3. departure_time: The time of day when the flight departs. Categories include:

* Evening
* Early_Morning
* Morning
* Afternoon
* Night
* Late_Night

4. stops: The number of stops the flight makes between the source and destination cities. Categories include:

* zero: Non-stop flight.
* one : Flight with one stop.
* two_or_more : Flight with two or more stops.

5. arrival_time: The time of day when the flight arrives at the destination. Categories include:

* Night
* Morning
* Early_Morning
* Afternoon
* Evening
* Late_Night

6. destination_city: The city where the flight lands. Categories include:

* Mumbai
* Bangalore
* Kolkata
* Hyderabad
* Chennai
* Delhi

7. class: The class of service in which the passenger is traveling. Categories include:

* Economy
* Business

8. days_left: No. of days remaining before departure date ranging form 1 to 49

Target variable:
* `price`: Price of the given airline flight.

Dataset Source Link :
[https://www.kaggle.com/datasets/shubhambathwal/flight-price-prediction?select=Clean_Dataset.csv](https://www.kaggle.com/datasets/shubhambathwal/flight-price-prediction?select=Clean_Dataset.csv)


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

Link : [EDA Notebook](notebook/EDA Airline Prices.ipynb)

# Model Training Approach Notebook

Link : [Model Training Notebook](notebook/MODEL TRAINING.ipynb)
