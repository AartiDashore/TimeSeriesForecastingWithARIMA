# Time Series Forecasting with ARIMA

This project demonstrates how to implement the ARIMA (AutoRegressive Integrated Moving Average) model for time series forecasting. The code trains an ARIMA model on a synthetic time series dataset, forecasts future values, and visualizes both the forecasted and historical data.

## Table of Contents
- [Overview](#overview)
- [Concepts](#concepts)
- [Explainations](#explanations)
- [Variables and Parameters](#variables-and-parameters)
- [Prerequisites](#prerequisites)
- [Usage](#usage)
- [Visualization](#visualization)
- [Applications](#applications)
- [License](#license)

## Overview
The ARIMA model is widely used for time series forecasting and can handle various types of time series data. This project covers:
- Generating synthetic time series data.
- Checking and ensuring the data is stationary.
- Applying the ARIMA model to forecast future values.
- Visualizing the forecasted values alongside the historical data.

## Concepts

### ARIMA Model
ARIMA stands for AutoRegressive Integrated Moving Average:
- **AutoRegressive (AR) Part**: Uses the dependency between an observation and a number of lagged observations.
- **Integrated (I) Part**: Involves differencing the raw observations to make the series stationary.
- **Moving Average (MA) Part**: Uses the dependency between an observation and a residual error from a moving average model applied to lagged observations.

### Stationarity
A stationary time series has constant statistical properties (mean, variance) over time. ARIMA models assume that the data is stationary, and if it is not, differencing is used to achieve stationarity.

### Forecasting
ARIMA models forecast future values based on past observations. The model provides predictions along with confidence intervals to account for uncertainty in the forecasts.

## Explanations

### Library Update:
The previous version used the deprecated ARIMA class from statsmodels.tsa.arima_model. The updated version uses the ARIMA class from the statsmodels.tsa.arima.model module, which is the correct and more up-to-date approach.

### Forecasting:
We use the get_forecast method from the ARIMA model to obtain the forecasted values and the confidence intervals. This method provides both the predicted values and the range of uncertainty (confidence intervals).

### Confidence Intervals:
confidence_intervals gives the lower and upper confidence bounds for the forecasted values, which are plotted as a shaded region around the forecast.

### ARIMA Model:
The ARIMA class takes the time series data and the model order (p, d, q) for training, where:
  - p: The number of autoregressive (AR) terms.
  - d: The number of differences needed to make the series stationary.
  - q: The number of moving average (MA) terms.

### Differencing:
We perform differencing on the time series to make it stationary, and then check stationarity using the Augmented Dickey-Fuller (ADF) test. If the series is non-stationary, it needs differencing to be made stationary.

### Plotting:
The plot shows both the historical data and the forecasted values. The confidence intervals are represented as a shaded area to indicate the uncertainty in the predictions.

## Variables and Parameters

### Dataset
- **`time_series_data`**: The input time series data used for training the ARIMA model. In this project, synthetic data is generated, but you can replace it with real-world time series data.

### Model Parameters
- **`arima_order`**: The order of the ARIMA model specified as `(p, d, q)`:
  - `p` = Number of AR terms
  - `d` = Number of differences to make the series stationary
  - `q` = Number of MA terms

### Forecasting
- **`forecast_steps`**: Number of future time periods to forecast.

### Confidence Intervals
- **`confidence_intervals`**: The range of uncertainty for the forecasted values.

## Prerequisites
Make sure to install the following Python libraries:
- `pandas`
- `numpy`
- `matplotlib`
- `statsmodels`

You can install them using:
```bash
pip install pandas numpy matplotlib statsmodels
```

## Usage

1. **Clone the Repository**:
   ```bash
   git clone https://github.com/your-repo/time-series-forecasting-arima.git
   cd time-series-forecasting-arima
   ```

2. **Run the Script**:
   To execute the ARIMA forecasting and visualization, run the Python script:
   ```bash
   python arima_forecasting.py
   ```

3. **Modify Parameters**:
   Adjust the dataset, ARIMA model order `(p, d, q)`, and `forecast_steps` in the script as needed.

## Visualization

### 1. **Historical Data and Forecasted Values**
The plot displays the historical time series data and the forecasted values. The forecasted values are shown in red, with confidence intervals represented by a shaded region.

### 2. **Forecasted Values**
The predicted future values based on the ARIMA model.

### 3. **Confidence Intervals**
The range of uncertainty in the forecast, which is displayed as a shaded region around the forecasted values.

Example plot:

Auto Correlation and Partial Correlation
![AutoCorrelation_and_PartialCorrelation](https://github.com/AartiDashore/TimeSeriesForecastingWithARIMA/blob/main/Output1.png)

Sarimax Results

![Sarimax_Results](https://github.com/AartiDashore/TimeSeriesForecastingWithARIMA/blob/main/Sarimax_results.png)

Forecast Plot:

![Forecast Plot](https://github.com/AartiDashore/TimeSeriesForecastingWithARIMA/blob/main/Arima_output.png)

## Applications

ARIMA models have a wide range of applications in various fields:

1. **Stock Market Forecasting**: Predicting future stock prices and market trends.
2. **Weather Prediction**: Forecasting weather conditions like temperature and precipitation.
3. **Demand Forecasting**: Estimating future product demand for supply chain and inventory management.
4. **Energy Consumption**: Predicting future energy usage for optimizing distribution and resource allocation.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

This `README.md` provides a comprehensive overview of the ARIMA forecasting project, including concepts, variables, usage instructions, and applications. It also includes placeholders for visualizations and provides practical details for running and modifying the code.
