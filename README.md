# Forecasting Covid - 19 in USA With ARIMA

It's a simple project that is done using time series analysis and forecasting it with ARIMA

## Introduction

Coronavirus disease (COVID-19) is a contagious infection caused by a newly discovered 
coronavirus. The majority of people infected with the COVID-19 virus will have a mild to 
moderate respiratory illness and will recover without any special treatment. People over the 
age of 65, as well as those with underlying medical conditions such as cardiovascular disease, 
diabetes, chronic respiratory disease, and cancer, are more likely to develop serious illnesses. 
However, due to the ability of the Covid-19 virus to mutate into multiple strains, currently there 
is no approved medication or drugs for Covid-19 patients other than vaccination. On December 
31, 2019, the World Health Organization (WHO) apparently received information from 
Wuhan, Hubei, China (Zhu et al., 2020), regarding an epidemic with an unknown origin.
This pandemic was formally designated COVID-19 on February 11, 2020 and was recognized
as an infectious illness causing a public health emergency since it swiftly spread throughout 
China and to a total of 24 nations. It is located geographically between 42.937084° N and 
75.6107° E. (Anderson et al., 2020). According to COVID-19 clinical trials, the majority of 
patients experience respiratory difficulties and pneumonia (Holshue et al., 2020)(Perlman, 
2020). COVID-19 causes kidney failure, pneumonia, and even death in the worst-case scenario, 
and symptoms reported in clinical treatments were similar to other coronavirus illnesses like 
MERS and SARS, such as cough, fever, and difficulty breathing due to respiratory disorder, 
and in the worst-case scenario, COVID-19 causes kidney failure, pneumonia, and even 
death(Wang et al., 2020). 
On January 15, 2020, the first COVID-19 patient was recorded in Washington State, and the 
coronavirus soon spread across the country, with the United States becoming the epicenter with 
the greatest deaths and patients or cases. After Wisconsin reported its first fatality on April 13, 
2020, COVID-19 has claimed the lives of at least one person in each of the 50 states in the 
United States. As of Jan, 2022, the worst-affected states in the United States are California 
(8.29M), Texas (6.19M), and Florida (5.5M). After COVID-19 spread quickly in Italy, France, 
and South Korea, prompting WHO to declare it a pandemic (Cucinotta & Vanelli, 2020).
The recent outbreak of COVID-19 in different states of India has major concerns for all 
administrative departments of the government and public. The Pandemic has been tested 
positive in 1287945 individuals with 817209 recovered and 30601 succumbed to the disease. 
The first case of the novel coronavirus was detected in India on 30 January 2020. The current 
study aims to develop an auto-regressive integrated moving average (ARIMA) model to predict 
the COVID-19 patients' rise, recovery and death in India based on the daily data obtained from 
the Indian government from 30 Jan 2020 to 3rd August 2020. Results clearly indicate that the 
predictions are well within the range of 95% confidence interval, except of the confirmed cases. 
But the main advantage of ARIMA forecasting approach is surely its ease of application and
interpretation.

## Methodology
![Figure 1](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%201.png?raw=true)

Figure 1.1 shows the methodology steps for the project. We first started with data collection 
from the New York Times GitHub, installed the required packages in Jupyter notebook, ran 
some preliminary exploratory data analysis, prepared the series for time series, ran the ARIMA 
time series, and lastly, the presentation and writing the report.
