# Predicting bike sharing demand using tree-based ensemble methods

This project uses AdaBoost, Random Forests and XGBoost to predict bike sharing demand in the metro DC area in the United States (data provided by Capital Bikeshare) using data between January 1, 2011, and December 31, 2018. The models are compared using three different performance measures (mean average error, root mean squared error, root mean squared log error) and compared against a naive baseline model (last value model).

## Table of Contents
* [Installation](#Installation)
* [Project Motivation and Description](#motivation)
* [File Description](#description)
* [Results](#Results)
* [Limitations](#Limitations)
* [Licensing, Authors, Acknowledgements](#licensing)

## Installation
The code requires Python versions of 3.* and general libraries available through the Anaconda package.

## Project Motivation and Description <a name="motivation"></a>
Climate change is forcing cities to reconsider their transportation infrastructure. Bike sharing is a more sustainable mode of transportation that reduces greenhouse gas emissions and other air pollutants. For bike sharing companies it is important to ensure that enough bikes are available at stations but not too many so that stations are not crowded with unnecessary bikes. Avoiding oversupply and shortages of bikes leads to happier customers and thus, knowing future demand becomes essential. There is already a broad body of literature that uses different features, algorithms, forecasting horizons and location-levels to predict demand in bike sharing systems.

However, there currently does not exist a comparison between different tree-based ensemble methods. These models have a number of advantages:
* ease of understanding and visualization of the algorithm
* yield better results than underlying weak learners
* nonparametric nature and ability to handle mixed data types
* robustness against overfitting, outliers, noise, multi-collinearity, and input scaling
* computationally relatively inexpensive

Therefore, this project wants to contribute to the research in the area of bike sharing demand to handle oversupply and shortages of bikes by answering the following research question:

#### How do tree-based ensemble models compare when predicting bike sharing demand?

To answer this question I used three different algorithms:
* AdaBoost
* Random Forests
* XGBoost

In addition to those three advanced machine learning models, I also used a naive baseline model (last value method) to compare the ML models' performances to a benchmark.

I used three different performance metrics to determine how well these models can predict bike sharing:
* MAE (mean average error)
* RMSE (root mean squared error)
* RMSLE (root mean squared log error)

## File Description <a name="description"></a>
This project includes two Jupyter notebooks, three pickled files and one csv file. The .ipynb file titled 'dataset_creation.ipynb' contains the code that creates the csv file 'bike_sharing_dataset.csv' that is used by the file 'bike_sharing_demand.ipynb' to implement the ML algorithms. The three different .sav files include the best saved ML models.

## Results
The main findings of the analysis will be published on [Medium](https://medium.com/@julia.nikulski). A short overview of the results shall be given here:

* The last value model is slightly outperforming all three ML models on the MAE --> this indicates that the ML algorithms are more moderately overpredicting compared to the last value approach which is more significantly deviating from the true value in more instances. This also means that the last value approach is rather good for predicting the demand of the next day compared to the advanced models which can be explained by the high autocorrelation of the target value
* XGBoost has the lowest MAE and RMSE of the three ML models while Random Forests has the lowest RMSLE --> this indicates that Random Forests overpredicts rather than underpredicts more often and heavily than the other two ML models
* Comparing the prediction of stationary versus non-stationary target values shows that XGBoost is performing slightly worse when non-stationary target values are used, while AdaBoost and Random Forests perform slightly better (except for the RMSLE)
* Analyzing how noise is handled by these algorithms by removing the weekday features (which only have small variations in the target distribution) shows that XGBoost is performing slightly worse without the weekday feature while AdaBoost and Random Forests are handling noisy data not as well, demonstrated by worse performances when the weekday features are included
* Comparing cross-validation times, XGBoost is the fastest model of the three ML models

## Limitations
There are a number of limitations of this project and the chosen implementation:
* lagged historical weather data was used to account for look-ahead bias and because weather forecast data is difficult to obtain --> the model results may have been better if forecast instead of realized weather from the day before would have been used
* the forecast horizon is only 1 day --> in reality, it would be necessary to add forecasts for multiple periods and for more periods in the future (1 week, 1 month, 6 months etc.)
* additional features aside from temporal and meteorological features could improve the ML model performances
* the three tree-based ensemble methods should be compared against other ML algorithms and more traditional statistical methods (e.g. ARIMA) so that their contribution to the overall aim of achieving accurate demand predictions can be assessed

## Licensing, Authors, Acknowledgements <a name="licensing"></a>
The data used for the analysis comes from:
* [Capital Bike Share](http://capitalbikeshare.com/system-data): this includes the bike demand data for the metro DC area
* [NOAA's National Climatic Data Center](https://www.ncdc.noaa.gov/cdo-web/search): this includes the weather data for the metro DC area
* [DC Department of Human Resources](http://dchr.dc.gov/page/holiday-schedule): this includes the holiday data for Washington, D.C.

Feel free to use the code as you please and play around with it.
