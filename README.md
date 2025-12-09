# Industrial Production Predictive Model

Incase the project file above return an error, you can alternatively access the file by clicking [here](https://nbviewer.org/github/abdulmumeen-abdullahi/Industrial-Production-Predictive-Model/blob/main/Industrial%20Production%20Predictive%20Model.ipynb).

## Overview of the Problem <br/>
Industrial production, particularly in utilities such as electric and gas, is a vital metric for assessing economic health and business performance. However, predicting industrial production trends is a complex task due to various influencing factors such as seasonality, demand fluctuations, and operational constraints. <br/>
This project aims to address this challenge by developing a predictive model that forecasts production trends using historical data. Accurate predictions can inform businesses and policymakers, enabling better resource allocation, operational planning, and policy formulation.
This project aligns with the United Nations Sustainable Development Goal 8: Decent Work and Economic Growth, by enabling data-driven decisions that support economic stability and growth through efficient resource utilization and predictive planning.

![image](https://github.com/user-attachments/assets/8806c0b8-b3fd-4e46-b84f-59bd4af0eb86)

## Data Used <br/>
The dataset for this project was sourced from the [Federal Reserve Bank of St. Louis](https://fred.stlouisfed.org/series/IPG2211A2N), containing the following two columns: <br/>
•	Date: The production date. <br/>
•	IPG2211A2N: The index value representing industrial production levels for electric and gas utilities (NAICS = 2211,2).

## Methodology <br/>

### 1. Data Preprocessing <br/>
•  Converted the Date column into a datetime format. <br/>
•  Set the datetime formatted date as the index for the dataframe. <br/>

### 2. Exploratory Data Analysis (EDA) <br/>
•  Plotted a time series graph to visualize trends in the IPG2211A2N index. <br/>
•  Calculated weekly rolling averages for trend smoothing and analysis. <br/>
•  Created a lag feature, IPG2211A2N.L1, to account for temporal dependencies in the data.

**Use of Lag by One**: The lag feature helps identify relationships between current and previous readings, enhancing the model's predictive accuracy. <br/>
•  Plotted a scatter graph to analyze correlations between current and lagged values.

### 3. Model Training <br/>
•  Split the dataset into 80% training and 20% testing sets. <br/>
•  Established a baseline model using the mean value of the target variable (IPG2211A2N) and calculated the Mean Absolute Error (MAE). <br/>
•  Utilized Autocorrelation (ACF) and Partial Autocorrelation (PACF) plots to determine optimal lag values for ARIMA and other models.

### 4. Model Selection and Evaluation <br/>
Trained and evaluated the following models: <br/>
•	**Linear Regression**: MAE = 8.5 <br/>
•	**Random Forest Regressor**: MAE = 8.4 <br/>
•	**Decision Tree Regressor**: MAE = 9.1

•	**Autoregressive (AR)**: <br/>
o	Achieved an MAE of 1.3 during training. <br/>
o	Performed well on the walk-forward validation test with an MAE of 3.31.

•	**Autoregressive Integrated Moving Average (ARIMA)**: <br/>
o	Achieved an MAE of 1.3 during training. <br/>
o	MAE on the walk-forward validation test was slightly higher at 3.72.

### 5. Model Explanation <br/>
•  Evaluated residuals (differences between actual and predicted values) using time series, histogram, and ACF plots. <br/>
•  Conducted walk-forward validation to assess future prediction accuracy. <br/>
•  Visualized the relationship between actual and predicted values on a time series plot.

## Results <br/>
•  Baseline Model: MAE = 27.1

**Best Performing Models**: <br/>
•	Autoregressive (AR): MAE = 1.3 (training), MAE = 3.31 (walk-forward validation). <br/>
•	ARIMA: MAE = 1.3 (training), MAE = 3.72 (walk-forward validation). <br/>
The AR model demonstrated the most significant reduction in error, outperforming the baseline by 25.8 points during training and 23.79 points in walk-forward validation.

## How the Model Can Help Businesses and Government Policy <br/>
This predictive model provides valuable insights into industrial production trends, enabling policymakers to forecast utility demand, plan infrastructure, and formulate sustainable energy policies. It also helps assess the impact of economic regulations on production. For businesses, the model optimizes operations, enhances supply chain management, and supports data-driven decision-making. By leveraging rigorous analysis, it achieves accurate predictions that can revolutionize industrial production forecasting. This tool is a significant step toward smarter, more sustainable government policies and business strategies.
