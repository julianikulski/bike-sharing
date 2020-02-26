# Predicting bike sharing demand using tree-based ensemble methods

This project uses AdaBoost, Random Forests and XGBoost to predict bike sharing demand in the metro DC area in the United States (data provided by Capital Bikeshare) using data between January 1, 2011, and December 31, 2018. The models are compared using three different performance measures (mean average error, root mean squared error, root mean squared log error) and compared against a naive baseline model (last value model). 

## Table of Contents
* [Installation](#Installation)
* [Project Motivation and Description](#motivation)
* [File Description](#description)
* [Results](#Results)
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




## Licensing, Authors, Acknowledgements <a name="licensing"></a>
The data used for the analysis comes from:
* [Capital Bike Share](http://capitalbikeshare.com/system-data): this includes the bike demand data for the metro DC area
* [NOAA's National Climatic Data Center](https://www.ncdc.noaa.gov/cdo-web/search): this includes the weather data for the metro DC area
* [DC Department of Human Resources](http://dchr.dc.gov/page/holiday-schedule): this includes the holiday data for Washington, D.C.

Feel free to use the code as you please and play around with it.
