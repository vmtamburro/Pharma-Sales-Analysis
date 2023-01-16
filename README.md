# Pharma Sales Analysis
This analysis was pereformed as a final project for Rutgers MSBA Course "Big Data Analytics". It consists of a data analysis and generated machine learning models based on open source research data collected by researcher Milanz Dravkovic from a single pharmacy's point-of-sales system. 


## Data Collection

Collected and groomed by researcher Milan Zdravković. The initial dataset was created from transactional sales data collected from a single pharmacy’s point-of-sales system.

The 57 drugs sold were then grouped to the Anatomical Therapeutic Chemical (ATC) Classification System Categories.
- M01AB - Anti-inflammatory and antirheumatic products, non-steroids, Acetic acid derivatives and related substances
- M01AE - Anti-inflammatory and antirheumatic products, non-steroids, Propionic acid derivatives
- N02BA - Other analgesics and antipyretics, Salicylic acid and derivatives
- N02BE/B - Other analgesics and antipyretics, Pyrazolones and Anilides
- N05B - Psycholeptics drugs, Anxiolytic drugs
- N05C - Psycholeptics drugs, Hypnotics and sedatives drugs
- R03 - Drugs for obstructive airway diseases
- R06 - Antihistamines for systemic use
- The data was collected for six years, with an incomplete final year.


## Contents
- Introduction
- Statistical Analysis
- Time Series Trends
- Long Term Trends
- Linear Regression Modeling
- Forecasting and Re-Ordering
- Conclusion


## Introduction
- Through this analysis data trends will be discovered and forecasting models will be created to predict long term generalized trends for specific drug groups. 
- These machine learning forecasting models and seasonality trends can be used to inform strategic re-ordering.
- Recommendations will be made for further analysis based on exogeneous variables. 


## Understanding the Data
- The data is presented in several views which include hourly, daily, weekly, and monthly point-in-time sales.
- For the purposes of this analysis, we assume that the values presented represent the number prescriptions filled.


Example Data Set:

![image](https://user-images.githubusercontent.com/43652134/212581314-c5af4472-ba74-472f-866b-d0157e302366.png)


## Descriptive Statistics Highlights
- Upon inspection of the descriptive statistics it can be noted that the daily, weekly, and monthly collected data increases proportionately for the mean, median, standard deviation. 
- It as also evident that the drug group N02BE is the most sold drug, and the drug group N05C is the least sold drug.
- There is also a high level of variance for the drug group N02BE, alluding to its seasonal influence which will be covered in later slides.

![image](https://user-images.githubusercontent.com/43652134/212581392-b4ede274-8b32-4c6a-aaf3-e4d1e00ab7c9.png)
![image](https://user-images.githubusercontent.com/43652134/212581396-d5237b94-2eae-4436-8ede-2ceb8b7a24d5.png)


![image](https://user-images.githubusercontent.com/43652134/212581480-16c3418a-b73c-4509-8ad3-3b9d1cbdc5e0.png)
![image](https://user-images.githubusercontent.com/43652134/212581492-b753cca1-8c92-42b8-b388-8c7baec4c1d1.png)
![image](https://user-images.githubusercontent.com/43652134/212581507-f7a3be58-eb09-4f44-8c45-899a890bf827.png)


## Time of Day
- The data was aggregated by average sales by time of day. Upon visualization it can be observed that on average the flux of drugs sold at various times of the day seems to differ based on these groups.
- Notably, N02BE has two peaks at 12:00PM, and 9:00PM with a steep drop in purchase frequency, while R03 has only an evening peak which has a more fluent onset.
- This could be perhaps due to the nature of the drug and the availability of the patients that are able to visit the store during those hours. The times seem to trend with a lunch time and evening time store visit.
- Given further customer demographic information and customer analysis, this could impact certain aspects of the business such as store staffing and shipment/loading scheduling. 

![image](https://user-images.githubusercontent.com/43652134/212581739-9cb11bd8-edf5-40c0-905c-e4084b797491.png)


## Time of Month
- Additionally, the data was aggregated by average sales by time of month. Several trends can be seen. 
- N02BE has a sharp spike in February and a smaller spike in October. This is an interesting trend as these drugs are generally painkillers, which one wouldn’t assume to have any type of seasonality, such as R06 which is an antihistamine for seasonal allergies.
- Seasonal trends can be observed for R06 aligning with Spring, Summer and Fall allergy seasons.
- With further data collection on patient diagnoses it may be worth investigating further into  the reason for N02BE trending as it is the highest selling drug of the pharmacy.

![image](https://user-images.githubusercontent.com/43652134/212581837-2895e4ac-5724-4aa9-b999-6695611ae0bb.png)


## Seasonality
- The data was split into three-year intervals for clarity of visualization. The data was then decomposed by drug group using an additive model, to indicate the impact of the seasonality.
- It can be observed that the impact of the seasons in the time series dataset is the greatest on NO2BE.


![image](https://user-images.githubusercontent.com/43652134/212581954-51bc1c7e-6f3a-4650-9ac4-209863869544.png)![image](https://user-images.githubusercontent.com/43652134/212581962-1ad9cbc5-73c3-4a22-a3d7-2960cae16950.png)



## Observing Long-Term Trends
- Because of the volatile sales volume changes due to seasonality, it was required to normalize the data with moving averages to get a scope of the long-term drug sale trends.
The following visualizations were created from 30, 120, and 365 day intervallic moving averages. A linear regression model was performed on the 365-day normalized averages, and three of the drugs displayed clear linear tendencies over the six years: R03, R06, and N02BA.
These trends can be indicative of effectiveness, comfort of prescription from medical providers, advertising, and potential endemic/pandemic tendencies.


![image](https://user-images.githubusercontent.com/43652134/212582066-6036170c-8b64-458b-8510-d43e98b884bb.png)
![image](https://user-images.githubusercontent.com/43652134/212582070-723d76c6-1c8c-4755-9437-240845ec3762.png)
![image](https://user-images.githubusercontent.com/43652134/212582080-4decbca5-7310-4413-879b-42b7ccfe8576.png)

## Linear Regressions
- N02BA Predictive Model - Reducing over Time
  - 76% Accuracy Training Score
  - 76% Accuracy Test Score
- R03 Predictive Model – Increasing Significantly
  - 83% Accuracy Training Score
  - 81% Accuracy Test Score
- R06 Predictive Model – Increasing Slightly
  - 70% Accuracy Training Score
  - 66% Accuracy Test Score



## Conclusion
- The forecasting models can be used to predict long term generalized trends for specific drug groups. These forecasting models and seasonality trends can inform strategic re-ordering of these drugs.
- It should be noted that while these predictions show the trends of sales, there are other factors that should also play a part in the re-ordering of a drug.
  - Pharma Capacities - Shelf/Stocking space availability
  - Price Optimizations
  - Essential Rescue drugs that must be kept on hand such as R03 which is used for obstructive airway diseases

## References
Pharma sales data. (n.d.). Www.kaggle.com. Retrieved December 18, 2022, from https://www.kaggle.com/datasets/milanzdravkovic/pharma-sales-data
‌
statsmodels.tsa.seasonal.seasonal_decompose — statsmodels. (n.d.). Www.statsmodels.org. 
https://www.statsmodels.org/dev/generated/statsmodels.tsa.seasonal.seasonal_decompose.html

sklearn.linear_model.LogisticRegression — scikit-learn 0.21.2 documentation. (2014). Scikit-Learn.org. https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LogisticRegression.html
![image](https://user-images.githubusercontent.com/43652134/212582231-81d74f53-3472-4ec6-ad17-7640c7682d22.png)









