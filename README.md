# DS4002-Project3-TeamNBC
# Title: MI2-Project3
# Group Name: Team NBC
# Members: Mianchen (Bruce) Cao, Nathan Patton, Camden Miller
# Leader: Nathan Patton
# Course: DS 4002
# Date: April 25th, 2023

# Research Question
Can we use a machine learning model to predict the market price of Apple stock in the near future? 

# Hypothesis
Stock market prices follow trends over time, so we can determine a range of possible future stock prices using machine learning algorithms at an accuracy greater than 60%.

# Modeling Approach
We need to test our hypothesis by trying to predict future ranges of stock market prices. One popular model to do this is known as a long short-term memory neural network (LTSM). LSTMs are one of the most useful and accurate time series models in making predictions about future trends. Our input dataset is a dataset found on Yahoo Finance containing stock market prices from the past five years, or 1259 days. There are seven total columns, but the columns of interest will be “Open” and “High”[1]. “Open” represents the opening price for shares that day and “High” represents the highest price of shares that day. Before building the LSTM model the following steps will occur: Data normalization and incorporating timesteps into data. The model will then be built, fitted, and used for forecasting, based on the training and test datasets. 

# Executive Summary
This document outlines the plan to use a time series model, known as LTSM, to make predictions about future stock trends. The established data set is detailed below focusing mainly on selecting the necessary variables from the dataset and cleaning. The analysis plan is provided with initial plans to use a LTSM model. 

# Data Set Establishment Details
After establishing a hypothesis and a research question that we think has solid motivation and value behind it, we searched for time series data sets that were not on kaggle. We found a dataset named “AAPL.csv” published by Yahoo Finance [1]. The dataset is accessible via the link in the reference section. The original dataset consisted of seven variables: Date, Open, High, Low, Close*, Adj Close**, and Volume. However, the only variables of interest here are the daily “Open” and “High” cost of the Apple stock. As mentioned in the Modeling Approach, in order for the data to fit a LTSM model, a few steps must be carried out with the current dataset. 

# Analysis Plan 
Once the dataset has been imported, the values of the second and third column, “Open” and “High”, will be selected as the training dataset. The training dataset will then be normalized between values of 0 and 1, so that the numeric columns are at a common scale, which helps the performance of the model. The input data for the LSTM model should be in the form of a 3D array, so data must be created in 60 time stamps so that numpy can convert it to the desired array. The LTSM model will then be built by carrying out the following processes: Initializing the neural network using Sequential, adding the LSTM layer using LSTM, preventing overfitting with dropout layers using Dropout, and adding densely connected neural network layer using Dense. The test dataset will then be imported and modified similarly to the training dataset, and the results of the predicted stock price and the actual stock price can be plotted. From this, the model’s performance can be evaluated, and we will adjust the parameters of the model depending on the result. The success of the model is based on the accuracy rate that the model gives us. We do not expect the exact price points from the predicted price to be the same as the actual price, but the model should be able to at least indicate overall trends of the curve. Attached below are the visualizations of our steps.

# Sources:
[1]	Yahoo! (2023, April 4). Apple Inc. (AAPL) stock historical prices & data. Yahoo! Finance.
Retrieved April 4, 2023, from https://finance.yahoo.com/quote/AAPL/history?period1=1522800000&period2=1680566400&interval=1d&filter=history&frequency=1d&includeAdjustedClose=true 

[2]	“Machine Learning to Predict Stock Prices | by Roshan Adusumilli | Towards Data         Science.”https://towardsdatascience.com/predicting-stock-prices-using-a-keras-lstm-model-4225457f0233 (accessed Apr. 15, 2023).
