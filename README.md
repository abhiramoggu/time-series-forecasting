# Multi-Step Univariate Time Series Forecasting of Renewable Energy Production


## 1. Project Objective

This project aims to achieve the following objectives:


#### 1. Conduct preliminary data analysis using descriptive statistics and data visualizations

- Calculate basic statistics like average, median, standard deviation, and range.
- Create visual representations to identify patterns and relationships within the data.

#### 2. Analyze the global trends, seasonality, and cyclicity in renewable energy production for historical information

- Identify trends over the historical period to understand how renewable energy production has changed over time.
- Identify cycles within the data, such as seasonal variations or cyclical fluctuations, which can provide insights into the factors influencing renewable energy production.

#### 3. Assess the relationship between renewable energy production and other energy sources

- Use statistical techniques to quantify the strength and direction of the relationship between renewable energy production and other energy sources, such as fossil fuels or nuclear energy.
- Create visualizations like scatter plots and correlation matrices to find associations between different energy sources.

#### 4. Test with different models to determine the best model for Univariate time series forecasting (static model at the moment)

- Experiment with various univariate time series forecasting models, such as ARIMA, to identify the best-suited model for predicting renewable energy production.

2. Evaluate the performance of each model using metrics to find  model that gives the most accurate forecasts.

#### 5. Multi-step forecasting of renewable energy production for the next few years

- Deploy the selected forecasting model to predict renewable energy production for multiple future time steps, considering the dynamic nature of renewable energy systems and external factors.
- Explore different scenarios and sensitivities to assess the potential impacts of various factors on future renewable energy production, aiding in decision-making and strategic planning.


## 2.Research Questions

This project poses to answer the following research questions:

#### 1. Analyze Temporal Trends

1. How did the global renewable energy production evolve over from 1973 - 2022?
2. Are there identifiable patterns or trends in renewable energy production on a global scale?
3. What factors have influenced the evolution of renewable energy production over time?

#### 2. Check for Endogenous Comparison

1. How does the growth rate of renewable energy production compare to that of fossil fuels and nuclear energy?
2. What are the correlations of renewable energy, fossil fuels, and nuclear energy production?
- UN Goals and Sustainable Development goals assert the need to switch from non-renewable sources like fossil fuels to renewable sources of energy. Hence, it is to be studied if an increase in renewable energy production reduces the need for fossil fuel production.
3. What insights can be gained from comparing the growth patterns of different energy sources?

#### 3. Check for Exogenous Variables

1. Were there any renewable energy policies or technological advancements influencing the growth and adoption of renewable energy sources globally?

#### 4. Seasonal and Climate Influences

1. How do seasonal variations and climate changes affect renewable energy production across different months and years?



## 3.Dataset Definition

In this time series forecasting project, the dataset is a multivariate chart that provides a comprehensive overview of global energy trends. The dataset covers monthly data from 1973 to 2022 and includes detailed information on energy production and consumption across various sources. These sources encompass fossil fuels, nuclear electric power, and renewable energy. Additionally, the dataset includes data on primary energy imports, exports, and stock exchanges. All energy measurements in this dataset are standardized in Quadrillion British Thermal Units (1 quad =
10^15 Btu). For this project, a univariate multi-step forecasting model will be deployed for renewable energy source production.

The source for this dataset comes from a Kaggle dataset titled "Global Energy Statistics (1980-2021).
<br> You can find the link here: https://www.kaggle.com/datasets/akhiljethwa/world-energy-statistics/data

This data was originally collected from the U.S Energy Information Administration website, which is the official,  reliable source for this study. You can find the link here: https://www.eia.gov/


## Conclusion

This report summarizes key findings of univariate time series forecasting og renewable energy production datasets from around the world based on information provided by eia.gov from the official website hosted by the United States through Kaggle.

#### Research Questions

**1. How did the global renewable energy production evolve from 1973 - 2022?**

The Total Renewable Energy Production shows an overall nonlinear increasing trend. From 1973 to 2000, production fluctuated between 0.4 and 0.6 quad Btu, peaking in 1984 and 1997, while from 2001 to 2022, it rapidly increased from just over 0.4 to nearly 1.2 quad Btu.


**2. What factors have influenced the evolution of renewable energy production over time?**

A sudden difference in trend from 2000 may indicate the availability of more data and changes in policies of renewable energy and more recent technological advancements and standardization of prices. These are exogenous variables.


**3. How does the growth rate of renewable energy production compare to that of fossil fuels and nuclear energy?**

The relationship between total renewable energy production and total fossil fuel production exhibits a moderately positive correlation and a somewhat linear pattern. Contrary to the expectation that an increase in renewable energy would correspond to a decrease in fossil fuels, both energy sources are increasing simultaneously, indicating that one is not replacing the other.


**4. What are the correlations of renewable energy production, fossil fuels, and nuclear energy production?**

There is a perfect positive correlation between total renewable energy and total renewable energy consumption, which is expected as higher demand correlates with higher production. Fossil fuels have a moderately positive correlation, while nuclear electric production and renewable energy production show a non-linear correlation.


**5. How do seasonal variations and climate change affect renewable energy production across different months and years?**

1. Solar Energy Exposure:

- Summer Months (May to August): High solar exposure leads to increased solar energy production, resulting in higher renewable energy output.
- Winter Months (September to December): Minimal solar exposure reduces solar energy production, leading to lower renewable energy output.
- Spring Months (January to April): Moderate solar exposure results in moderate renewable energy production, as the sun exposure is neither too low nor too high.
- These trends were identified for three sets of 15 years from 1975 to 2020, and there were some changes identified for which more reasons are explained as follows.

2. Seasonal Changes in Climate:

- Global Warming: Changes in climate due to global warming might have made spring months warmer, increasing solar energy production during these months.
- Contribution of Wind and Tidal Energy: These smaller contributors to renewable energy generation record medium levels of production, which is reflected in the moderate energy production observed during the transition months between seasons.

3. Policy Changes and Technological Advancements:

- Policy Changes: Variations in renewable energy production across different months and years may also be influenced by changes in policies promoting renewable energy.
- Technological Advancements: Improvements in renewable energy technologies could lead to increased production during certain periods.

#### Model Evaluation

- ConvLSTM Model: Best overall performance with RMSE: 0.049657, MAE: 0.038772, and MAPE: 4.093273%, effectively capturing both trends and fluctuations.
- Vector Output Model: Strong performance in multi-step forecasting with tight prediction bundling, RMSE: 0.056716, and MAE: 0.046123.
- Univariate CNN: Effective for univariate predictions, capturing trends and seasonality well with RMSE: 0.048757 and MAE: 0.038186.
- Multi-step CNN: Useful for longer horizon forecasts, capturing future trends effectively with RMSE: 0.072331 and MAE: 0.057219.
- Multivariate CNN: Leveraging additional features (consumption and fossil fuel production) improves accuracy, RMSE: 0.034249, and MAE: 0.027702.
- LSTM Variants: Bidirectional, CNN-LSTM, Vanilla, and Stacked LSTM capture different temporal patterns, but ConvLSTM outperforms them in accuracy.
- Encoder-Decoder Model: Slightly less accurate than the Vector Output Model with RMSE: 0.060508 and MAE: 0.048020, but effective in handling variable-length sequences.
- Grid Search was experimented over three models, namely Dense Layer, CNN, and LSTM. The best configuration for each is [12, 100, 100, 1, 0], [12, 64, 5, 100, 150, 12], [12, 100, 50, 150, 12], with RMSE values at 0.056, 0.050, 0.05,3, respectively. This makes CNN comparatively the better performer, followed by LSTM and Dense Layer.


