# Forecasting_AQI_Cincinnati_Time_Series_using_Quarto

### Part-I : Exploratory Data Analysis
**Section 1:** is describing the time series dataset selected, its source and answering why this dataset in particular? Discussing some potential explanations of the data-geneating process. What drives variation in the variable? Why or why not this might be an easy/difficult variable to forecast?

**Section 2:** involves exploratory data analysis to describe the behavior of the time-series along with various summary statistics of the data, to include standard metrics such as the number of observations of the time series, its mean, median, and mode, as well as standard deviation, range, etc. Checking for any obvious patterns that can be described based on what we know about the data-generating process

**Section 3:** involves visualizing a moving average of the time series variable and the “remainder” series calculated by subtracting the moving average from the original time series. Does there appear to be other patterns in the data that are not captured by the moving average? Does the remainder time series appear to be white noise? Assessing if the time series contains seasonality using a time series decomposition.

**Section 4:** is conducting a 6 point naive forecast of the time series to set as a benchmark

### Part-II : Fitting ARIMA Model
**Section 1:** is assessing the behavior/data-generating process of the time-series. If the data appears to be variance non-stationary (using a rolling SD or other method), transform the time-series using a natural log or Box-Cox transformation. If seasonality is present, use seasonal differencing to remove the seasonal. Use KPSS test to check for mean stationarity after performing the above operations (if necessary) and if the process is mean non-stationary, calculate the first difference of the data (after log/Box-Cox and seasonal differencing) and visualize it.

**Section 2:** Interpreting ACF/PACF plots of the transformed time series after the above operations. Based on the ACF/PACF alone, does the time-series appear to be an autoregressive process, moving average process, combined, or neither? What might you suspect the order of the time-series to be (e.g. ARIMA(0,1,2)) using the ACF/PACF plots and stationarity tests? If the data contain a seasonal component, describe any seasonal ARIMA effects (PDQ) that may be interpretable from the ACF/PACF plots.

**Section 3:** Fitting ARIMA models to the time-series variable based on the “best guesses” and “best” according to the AIC or BIC? After selecting the best model, derive the fitted values for the time series and plot them against the observed values of the series. Do the in-sample predicted values tend to follow the trends in the data?

**Section 4:** Compute and analyze the residuals from the selected model. Conduct a Box-Ljung test for residual autocorrelation and examine the ACF/PACF plots in the residuals. Do the residuals appear to be white noise? If the residuals do not appear to be white noise, test different models until you find the best one for which the residuals are closest to white noise. Finally, creating a 6 time-period forecast for your model from the end of the data.

Note: We can use auto.arima() or the automated ARIMA function from fable to find the “best” model.

### Part-III : Fitting Facebook Prophet Model
**Section 1:** is fitting and assessing a Facebook Prophet model to the time series.

**Section 2:** Decompose and visualize the elements of the time-series (trend, seasonality, etc.) as identified by the initial model. Examine the changepoints identified for the “trend” part of the time series. Do these detected changepoints make sense for your time-series? If not, adjust the hyperparameters of the model by specifying more or fewer changepoints (n_changepoints), or by changing the proportion of the time-series through which changepoints can be identified (changepoint_range), or the prior scale (changepoint_prior_scale). Also assess whether a linear or logistic trend makes sense for your time-series and whether the model should take into account a saturating minimum/maximum point - if so, specify a floor and cap.

**Section 3:** Checking is any seasonality is identified by the model (daily, weekly, yearly, etc.). Does the time series seem to contain additive or multiplicative seasonality? If appropriate, and while examining daily data, assessing whether holidays should be included in the model.

**Section 4:** Conduct a rolling window cross-validation to assess performance of the model at meaningful thresholds depending on the data. Finally, creating a 6 period forecast using the best fit Prophet model.


References:
1. Spring'23 - BANA 7050: Time Series Forecasting by Dr.Antony, Alex
2. Hyndman, R.J., & Athanasopoulos, G. (2021) Forecasting: principles and practice, 3rd edition, OTexts: Melbourne, Australia. OTexts.com/fpp3.

