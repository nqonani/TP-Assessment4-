Time Series Forecasting for Local Businesses - Assessment Report
1. Overview
In this assessment, I implemented three machine learning models—Prophet, ARIMA, and LSTM—to forecast sales data for spaza shops in South Africa. The goal was to predict future sales and make recommendations based on the predictions. This document explains each step taken to create the dataset, the modeling process, errors encountered, and why the LSTM model could not be completed.

2. Dataset Creation
To start the assessment, I manually created a dataset representing daily sales data for multiple shops across various South African provinces.
After creating the dataset, I saved it into a CSV file for further processing in Python.

3. Modeling Process
3.1. Prophet Model

I renamed the Date column to ds and Sales (ZAR) column to y to align with the Prophet model’s expected input format.
The data was cleaned and missing values were handled.

3.2. ARIMA Model

I used ARIMA from the statsmodels library to forecast sales. The dataset was transformed to ensure it followed the stationarity requirement for ARIMA modeling.
Model Fitting:

3.3. LSTM Model

To use the LSTM model, I needed to scale the data between 0 and 1 using the MinMaxScaler from sklearn.

I attempted to implement an LSTM model using TensorFlow. However, I encountered an error that prevented me from continuing with LSTM.
This error occurred while importing TensorFlow due to an issue with my local environment setup. Despite attempting various fixes (such as reinstalling TensorFlow and updating system configurations), I was unable to resolve the error. As a result, I could not complete the LSTM model.

Cause: The error was related to TensorFlow’s inability to load its internal modules on my system. This issue is common on Windows environments when there are compatibility issues with TensorFlow and the local machine setup.

4.Fix Attempts:

I tried reinstalling TensorFlow and ensuring that all dependencies were correctly installed.
Checked TensorFlow’s documentation for possible fixes but was unable to resolve the issue within the available timeframe.
5. Conclusion
Due to the errors encountered, I was unable to complete the LSTM model.

Key Takeaways:

The Prophet model was relatively easy to set up and performed well for short-term forecasting.
ARIMA required more preprocessing but also produced accurate forecasts.
The LSTM model was not completed due to the TensorFlow import error, which could not be resolved.

During this assesment I had the following question "When was the future dataframe created, and how?"
To which I discovered:

When:
The future dataframe is created after the Prophet model has been trained. It is generated using the .make_future_dataframe() method provided by Prophet.

How:
You specify the number of periods (days, weeks, months) into the future that you want to predict. Prophet will then create a dataframe with a ds column containing all the future dates where the model will predict sales. The number of future periods is specified using the periods argument.
22354757 Gumede N