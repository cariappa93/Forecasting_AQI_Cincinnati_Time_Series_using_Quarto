# Forecasting_AQI_Cincinnati_Time_Series_using_Quarto

### Part-I
**Section 1:** is describing the time series dataset selected, its source and answering why this dataset in particular? Discussing some potential explanations of the data-geneating process. What drives variation in the variable? Why or why not this might be an easy/difficult variable to forecast?

**Section 2:** involves exploratory data analysis to describe the behavior of the time-series along with various summary statistics of the data, to include standard metrics such as the number of observations of the time series, its mean, median, and mode, as well as standard deviation, range, etc. Checking for any obvious patterns that can be described based on what we know about the data-generating process

**Section 3:** involves visualizing a moving average of the time series variable and the “remainder” series calculated by subtracting the moving average from the original time series. Does there appear to be other patterns in the data that are not captured by the moving average? Does the remainder time series appear to be white noise? Assessing if the time series contains seasonality using a time series decomposition.

**Section 4:** is conducting a 6 point naive forecast of the time series to set as a benchmark

### Part-II
**Section 1:** is assessing the behavior/data-generating process of the time-series. If the data appears to be variance non-stationary (using a rolling SD or other method), transform the time-series using a natural log or Box-Cox transformation. If seasonality is present, use seasonal differencing to remove the seasonal. Use KPSS test to check for mean stationarity after performing the above operations (if necessary) and if the process is mean non-stationary, calculate the first difference of the data (after log/Box-Cox and seasonal differencing) and visualize it.

**Section 2:** Interpreting ACF/PACF plots of the transformed time series after the above operations. Based on the ACF/PACF alone, does the time-series appear to be an autoregressive process, moving average process, combined, or neither? What might you suspect the order of the time-series to be (e.g. ARIMA(0,1,2)) using the ACF/PACF plots and stationarity tests? If the data contain a seasonal component, describe any seasonal ARIMA effects (PDQ) that may be interpretable from the ACF/PACF plots.

**Section 3:** Fitting ARIMA models to the time-series variable based on the “best guesses” and “best” according to the AIC or BIC? After selecting the best model, derive the fitted values for the time series and plot them against the observed values of the series. Do the in-sample predicted values tend to follow the trends in the data?

**Section 4:** Compute and analyze the residuals from the selected model. Conduct a Box-Ljung test for residual autocorrelation and examine the ACF/PACF plots in the residuals. Do the residuals appear to be white noise? If the residuals do not appear to be white noise, test different models until you find the best one for which the residuals are closest to white noise. Finally, creating a 6 time-period forecast for your model from the end of the data.

Note: We can use auto.arima() or the automated ARIMA function from fable to find the “best” model.


