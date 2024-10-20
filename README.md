# NYC Taxi Fare Prediction

## Overview

This project aims to build a predictive model to estimate taxi fares in New York City using various factors, including trip details and weather conditions. The analysis and prediction utilize tools such as PySpark, Spark SQL, and Python, supplemented by libraries from the Python ecosystem. The project explores relationships between the fare amount and various features of the trips, and the goal is to optimize the model to provide accurate fare predictions.

## Problem Statement

The objective of the project is to develop a model capable of predicting the taxi fare amount for yellow taxis in New York City. Factors considered include trip distance, pickup and drop-off locations, number of passengers, and weather conditions. The model provides insights for stakeholders to optimize resource allocation and better understand fare determinants.

## Prerequisites

Ensure the following tools and libraries are installed:

- Python 3.x
- PySpark
- Spark SQL
- Pandas
- Scikit-learn
- NumPy
- Matplotlib
- Google BigQuery (for weather data)

Install dependencies using:

```bash
pip install pandas scikit-learn numpy matplotlib pyspark
```
## Data Collection
Data was sourced from:
- NYC Yellow Taxi trip data (January and February 2023) from the NYC.gov website.
- Weather data from NOAA’s Global Surface Summary of the Day dataset, retrieved through Google BigQuery.

The dataset contains over 500k rows and 43 columns after preprocessing.

## Data Preprocessing
The preprocessing steps included:
- Removal of null values (indicating canceled rides or no-shows).
- Filtering trips by:
  - Trip distance between 1 and 100 miles.
  - Fare between $3 and $200.
  - Passenger count less than 5.
- Creation of new time columns, such as day of the week and week number.
- Conversion of string-encoded weather data columns to integer format.

## Exploratory Data Analysis (EDA)
Several analyses were performed:
- **Distribution of fares**: Visualized by borough, showing common fare ranges across NYC.
- **Impact of passenger count**: No significant correlation between the number of passengers and the fare amount.
- **Trip distance**: Shorter trips are more frequent, with a steep decrease as distance increases.
- **Pickup and drop-off heatmaps**: Concentrated taxi activity in central Manhattan and airports.
- **Temporal patterns**: Variations in trip counts by day of the week and week of the month.
- **Weather influence**: No strong correlation between weather conditions and average fares, but slightly fewer trips on rainy days.

## Data Modeling
Three regression models were implemented for fare prediction:
1. **Linear Regression**
2. **Random Forest Regressor**
3. **Decision Tree Regressor**

## Model Training and Evaluation
The dataset was split into 80% training and 20% testing sets. The models were evaluated using the Root Mean Square Error (RMSE) metric:
- **Linear Regression**: RMSE = 3.75
- **Random Forest Regressor**: RMSE = 4.22
- **Decision Tree Regressor**: RMSE = 3.71

The results indicate that Linear Regression and Decision Tree Regressor performed comparably well.

## Key Insights
- **Fare distribution**: Most trips have fares between $10 and $20, with occasional outliers for airport trips.
- **Weather effect**: People tend to avoid traveling during high precipitation days.
- **Weekly patterns**: Slight dip in rides during Sundays and at the end of the month, potentially due to reduced demand.
- **Airport trips**: Fares to/from airports like JFK, LaGuardia, and Newark have consistent fare ranges, likely reflecting standard rates.

## Challenges
The primary challenge was the volume of the dataset. Due to processing limitations, only data from January and February were used. Expanding the dataset to include more months would likely improve model accuracy and lower RMSE.

## Future Work
Future improvements include:
1. Using a full year’s worth of data for a more robust model.
2. Hyperparameter tuning of the Random Forest model to reduce overfitting.

## Usage
1. Clone the repository.
2. Install the necessary dependencies.
3. Run the Jupyter Notebook (`NYC_Taxi_Fare_Prediction.ipynb`) to train and evaluate the model.

## License
This project is licensed under the MIT License.

## Acknowledgments
This project is a collaboration between team members:
- Navya Kiran V B (SUID: 291769531)
- Jovita Andrews (SUID: 522110149)

Data was sourced from NYC.gov and NOAA’s Global Surface Summary of the Day dataset.
