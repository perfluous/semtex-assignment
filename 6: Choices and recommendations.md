# Time Series Forecasting: Prophet & SARIMA

## Explanation of the Selected Algorithm and Approach

### Prophet

We employed the Prophet forecasting tool, designed for forecasting time-series data. Prophet is tailored for datasets with strong seasonal effects and several seasons of historical data. The algorithm decomposes the time series into trend, yearly seasonality, weekly seasonality, and holiday effects.

#### Why Prophet?

- **Automatic Detection of Seasonality**: Prophet detects the seasonality in the data, ideal for intricate seasonal patterns.
- **Handles Missing Data**: Prophet manages missing data points.
- **Flexibility with Large Datasets**: Prophet is optimized for extensive datasets.
- **Regressors**: External regressors (like temperature) can be incorporated, adding versatility.

#### Foundational Assumptions:

- **External Regressors**: We assume that external factors, like temperature, have a significant impact on the energy usage. This is why we include them as regressors in the Prophet model.
- **Stationarity (for some algorithms)**: Some algorithms like ARIMA assume that the data is stationary, meaning statistical properties like mean, variance remain constant over time.


### Alternative: SARIMA (Seasonal AutoRegressive Integrated Moving Average)

The SARIMA model is adept at handling time series data with seasonal patterns, making it suitable for predicting heat demand with seasonal variations.

#### Components of SARIMA:

- **AR (AutoRegressive)**: Models the relationship between an observation and lagged observations.
- **I (Integrated)**: The number of differences needed for time series stationarity.
- **MA (Moving Average)**: Models the relationship between an observation and a residual error from a moving average model.
- **Seasonal Components**: Captures seasonal patterns.

## Potential Alternatives:

- **LSTM**: LSTMs are a type of RNN architecture designed for sequence prediction.
- **Time Series Regression**: Regression algorithms predict future time series values. External regressors can be added.

## Recommendations for Enhancements:

- **Hardware Upgrade**: Enhance model training times with upgraded hardware or cloud solutions.
- **Enriching the Data**: Incorporate more data points or features, such as weather conditions or special events.
- **Model Ensembling**: Combine predictions from different models for better accuracy.
- **Advanced Model Tuning**: Enhance the grid search with methods like Bayesian optimization. This was tried but not included in the final model due to time/hardware constraints.
- **Feature Engineering**: Extract additional features for improved forecasting accuracy.
- **Domain Research**: Understand domain-specific intricacies, such as building insulation or heating systems.
- **Regular Model Updates**: Periodically retrain with new data.
- **Deep Learning Approaches**: Use models like LSTMs or GRUs for large datasets.
- **Anomaly Detection**: Integrate a system to identify unusual energy use patterns.

