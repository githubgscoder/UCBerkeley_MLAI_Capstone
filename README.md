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
The results of this project will be presented in the following format:
1. Summary of the best model selected based on ACF and PACF plots.
    - Based on thsese
    ![ACF and PACF Graphs](image.png)
2. Evaluation metrics such as Mean Absolute Error and Root Mean Square Error.
3. Comparison of the performance of the selected model with and without external factors.
4. Visualizations of the predicted census data and staffing needs.
5. Recommendations for implementing the final model in a production environment.
6. Additional models used to provide a summary and trace the best model.
7. A summary of the project's findings and implications for healthcare organizations.
8. Future work and potential areas for improvement.
9. A discussion of the limitations of the study and potential biases.
10. A conclusion summarizing the main findings and takeaways.


#### Next steps
What suggestions do you have for next steps?

#### Outline of project

- [Link to notebook 1]()
- [Link to notebook 2]()
- [Link to notebook 3]()


##### Contact and Further Information