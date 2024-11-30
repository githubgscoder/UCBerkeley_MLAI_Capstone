### Project Title
Predicting staffing needs based on predicted census data

**Author**
Gigo Samuel

#### Executive summary
This project aims to predict staffing needs for a healthcare organization based on predicted census data. The goal is to develop a time series forecasting model using ARIMA or SARIMAX to accurately predict patient census and optimie staffing levels in a healthcare setting. 

#### Rationale
Why should anyone care about this question?
Labor cost is a significant expense for healthcare organizations. Accurate staffing levels can help reduce labor costs, improve patient satisfaction, and enhance the overall quality of care. Predicting staffing needs based on predicted census data can help healthcare organizations optimize their staffing levels, reduce overtime, and ensure patients receive the care they need.

#### Research Question
What are you trying to answer?
This project aims to answer the following research question:
1. Can we develop a reliable time series forecasting model to predict patient census?
2. Can we use the predicted census data to accurately forecast staffing needs?
3. Can external factors be used to help improve the accuracy of the forecasting model?


#### Data Sources
What data will you use to answer you question?
The following data sources will be used:
1. Historical patient census data (daily counts of patients in the hospital), internal from the hospital's electronic health record system. 
2. External data source - CalHHS | Percentage of Influenza Detections at Clinical Labs - [Link](https://data.chhs.ca.gov/dataset/respiratory-virus-weekly-report/resource/877467c6-ace4-4ccd-9d83-079c8c968d5a)

#### Methodology
What methods are you using to answer the question?
The following methods will be used:
1. Data Preprocessing: Cleaning and transforming the data to prepare it for modeling.
2. Time Series Decomposition: Decomposing the time series data into trend, seasonality, and residual components.
3. Model Selection: Selecting the best ARIMA or SARIMAX model based on the Auto-Correlation and Partial Auto-Correlation (ACF and PACF) plots.
4. Model Evaluation: Evaluating the performance of the selected model using metrics such as Mean Absolute Error and Root Mean Square Error.
5. Model Refining: Refining the model by incorporating external factors such as influenza detections.
6. Additonal Models: Using Auto ARIMA to provide a summary and trace the best model.
7. Model Deployment: Deploying the final model to predict staffing needs based on predicted census data.


#### Results
What did your research find?
- Was able to derieve the p,q values from the ACF, PACF plots
      ![image](https://github.com/user-attachments/assets/41c6d8e0-99ab-424a-8b0b-5cb1981e6534)

- While we applied 3 additional features, weekday, month and flu percentage to the dataset and scaled them, the only additional feature that helped reduce the RMSE and MAE was the flu percentage.
      ![image](https://github.com/user-attachments/assets/4cd2701b-cc02-4253-aaa5-35545985f863)

- The best model was a SARIMAX model with an order of (1,1,1) and seasonal order of (0,0,0,0) with a period of 110 and seasonal period of 5. 
      ![image](https://github.com/user-attachments/assets/39ba138a-628b-47d0-859b-600b2dcc7c70)

- While Auto-ARIMA(AA) had the lowest RMSE and MAE, while copmaring the forecast by AA and STLForecast, it was better to use the STLForecast as there was a steady change in the census that matched more or less with the actual census
      ![image](https://github.com/user-attachments/assets/d598b592-2949-4055-8aa5-6d5880d601f7)
      ![image](https://github.com/user-attachments/assets/62ccb21e-f7f5-4c6c-8f2b-4b73125876c2)

- The number of staff reuqired were calculated based on the census predicted and while we could use either AA or STLForecast, it was decided to use STLForecast and adjust for changes as needed.
      ![image](https://github.com/user-attachments/assets/38649ccd-6daf-4cfb-9190-4019b03d6c4f)




#### Next steps
What suggestions do you have for next steps?
- While this project only emphasized on looking at one department, it would be good to see the predictions of the other departments.
- Incorporate more features like hospitalization if data exists
- As there are many variables that could be considered for patients to be admitted, it would be good to test out to see if there is lag in how the admission increase based on weekly flu percentage. Do we see admission increase a week after flu trends upwards, etc.?

#### Outline of project

- [[Link to notebook 1]()](https://github.com/githubgscoder/UCBerkeley_MLAI_Capstone/blob/5dcab1897fac145b3d39992832bae7181a76b744/Capstone_GS.ipynb)


##### Contact and Further Information

Visualizations:

- Census vs Percentage of positive FLu cases tested
  ![image](https://github.com/user-attachments/assets/be1677c0-c3ba-4977-971f-3e6778d19dae)

- Seasonal Decomposition

  ![image](https://github.com/user-attachments/assets/e245f8f0-5c8d-4525-9117-9f546c1387aa)

- Autocorrelation and Partial Autocorelation
  ![image](https://github.com/user-attachments/assets/635f01d9-88cd-4eae-810a-fe3e28d1d8b8)

- Historical and Future Census Plot
  ![image](https://github.com/user-attachments/assets/15e9da01-6c98-407c-916e-76b816a252c2)

- Forecasting using just ARIMA
      ![image](https://github.com/user-attachments/assets/d4b2984c-0f82-4f0a-abaa-afcd3a6f7769)

- Trend Extraction from the ARIMA model
  ![image](https://github.com/user-attachments/assets/c87b5e76-5708-4187-8bfd-c47cc2126a2f)

- STLForecasting with ARIMA with order (3,0,1) and scaled features only
  ![image](https://github.com/user-attachments/assets/44ea47fc-c66c-43be-9ac6-a10818bf2bb3)

- STLForecasting with ARIMA with order (3,0,1) and unscaled features only
  ![image](https://github.com/user-attachments/assets/85074526-d821-4c8c-9936-6ca550ab4ef0)

- STLForecasting with ARIMA with order (3,0,1) with one feature "perFlu"
  ![image](https://github.com/user-attachments/assets/fc6edbca-dd7e-490b-b1f7-e7014d870f0a)

- STLForecasting with ARIMA with order (3,0,1) with two unscaled features excluding "perFlu"
  ![image](https://github.com/user-attachments/assets/b62ea9ed-90e2-44ef-8d9c-471370b2f1c9)

- Auto-ARIMA and STLForecasting using SARIMAX with an order of (1,1,1) with one Feature "perFlu"
  ![image](https://github.com/user-attachments/assets/44e54d6f-dbca-4ced-bc4f-bd372777ea03)

- Actual Census vs Predicted Census using Auto-ARIMA and STLForecast with Predicted staffing for both models
  ![image](https://github.com/user-attachments/assets/fda7650d-e03a-46ba-8a01-c3727798d713)









