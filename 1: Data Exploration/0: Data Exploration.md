# Preliminary Data Exploration

## Objective
Develop a forecasting algorithm to predict the hourly heat demand of the "Semtex OFFICE" building for the next week, using available datasets and correcting the identified erroneous “-” values in the dataset. The datasets are provided in CSV format with columns such as ‘UTC’, ‘S31 Heat demand (%)’, ‘S32 Heat demand (%)’, ‘S41 Heat demand (%)’, ‘Outside temp (0.1 °C)’, and ‘Building Semtex OFFICE (kWh)’. The data is formatted as an averaged hourly time-series.

## Progress & Insights

### Data Exploration and Cleaning
- Explored the dataset, identified unusual “-” values, and replaced them with NaN.
- Investigated clustering of erroneous entries and their distribution over different periods, especially during colder periods and non-operational hours.
- Analyzed relationships between different features, focusing on the 'Outside temp (0.1 °C)' and 'Building Semtex OFFICE (kWh)'.
- WARNING: Package openpyxl changes '-' values to '0'. A manual copy has been made to keep the faulty values in the data.
- WARNING: Manual save of CSV file does not compute millisecond range. Hard copy of range has been done to Semtex_Assignment.csv

### Modeling Approach
- Chose the Prophet model from Facebook due to its capabilities and simplicity for time-series forecasting.
- Addressed issues related to missing regressors and NaN values during model implementation and training.
- Assessed model performance using MAE, obtaining a value of 9.419.41 on the validation dataset.

### Advanced Analysis
- Developed functions to perform detailed analysis on the erroneous data inserts, including frequency analysis, clustering analysis, statistical tests, entropy analysis, and date-time analysis.

### Domain Research
- Understood the importance of domain knowledge by reviewing papers on the topic and planning to leverage this knowledge for further analysis, feature engineering, and model refinement.

## Next Steps

### Data Imputation
- Decide on a strategy to impute the NaN values, leveraging domain knowledge and potentially using a suitable regression model or time-series imputation methods.

### Model Refinement and Evaluation
- Refine feature engineering, optimize model parameters, retrain the model including all features, and finalize the model for forecasting.
- Evaluate the refined models using appropriate evaluation metrics and cross-validation.

### Further Exploration and Analysis
- Continue with more detailed EDA, domain research, and the development and evaluation of preliminary models.
- Run modified advanced analysis functions on actual datasets to refine the analysis based on obtained results and any new requirements or constraints.

## Building Heat Demand Metrics

### S31 Heat demand (%)
- **Mean:** 0.000122
- **Std:** 0.000087
- **Min:** 0.000010
- **Max:** 0.000359

### S32 Heat demand (%)
- **Mean:** 0.000120
- **Std:** 0.000079
- **Min:** 0.000023
- **Max:** 0.000360

### S41 Heat demand (%)
- **Mean:** 0.000131
- **Std:** 0.000108
- **Min:** 0.000008
- **Max:** 0.000399

### Outside temp
- **Mean:** 10.031
- **Std:** 6.982
- **Min:** -11.000
- **Max:** 32.100

### Building Semtex OFFICE (kWh)
- **Mean:** 24.899
- **Std:** 17.924
- **Min:** 3.310
- **Max:** 68.180

## Observations

### Normalized Heat Demand Profiles
The heat demand profiles for buildings S31, S32, and S41 have similar patterns, showing fluctuations that might be related to the time of the day or outside temperature.

### Outside Temperature
The outside temperature shows fluctuations, possibly indicating daily temperature variations.

### Building Semtex OFFICE Heat Demand
The heat demand of the Semtex OFFICE building also shows fluctuations and appears to have patterns corresponding to the time of the day.

## Pattern Analysis
Outside temp (0.1 °C) data:
- " - "

### Timestamps
These missing values do not appear to be at regular intervals, and the dates range across multiple months. However, seasonality and temperature patterns have been observed in the data.

### Specific Times
Most of the missing values are either late at night or early in the morning, which might suggest a pattern, these have been found to generally be outside work hours or in the weekends.

### Heat Demand Values
The heat demand values during these times do not show an obvious pattern; they are not consistently high or low when the temperature data is missing.

## Analysis of Unusual Values in Historic Data

### Frequency Analysis
- **Total Entries:** 8760
- **Erroneous Entries:** 20
- **Valid Entries:** 8740
- **Conclusion:** A very small proportion of the dataset has erroneous entries.

### Temporal Clustering Analysis
- **Mean Time Difference:** 442.16 hours
- **Standard Deviation:** 1194.46 hours
- **Minimum Time Difference:** 1 hour
- **Maximum Time Difference:** 5327 hours
- **Conclusion:** Erroneous entries are spread out across the dataset without significant clustering.

### Statistical Tests
- **Chi Square Statistic:** 8680.18
- **P Value:** 0.0
- **Conclusion:** The occurrence of erroneous entries significantly differs from a uniform distribution, suggesting a non-random occurrence.

### Entropy Analysis
- **Entropy:** 0.0233
- **Conclusion:** The dataset is highly ordered, and the occurrence of erroneous entries is not completely random.

### Date-Time Analysis
- **During Work Hours:** 0
- **Outside Work Hours:** 12
- **Weekends:** 8
- **Conclusion:** Erroneous entries tend to occur outside work hours and on weekends, indicating a possible pattern related to operational hours.

## Overall Conclusion
The erroneous values are few and are not uniformly distributed. They tend to appear outside work hours and on weekends, indicating a higher degree of order in their occurrences.


