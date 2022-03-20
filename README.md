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

### Dataset
The dataset was obtained from https://github.com/nytimes/covid-19-data. The 2 CSVs 
used were us.csv file containing USA National Daily COVID-19 cases and deaths from 2020 
to 2022, as well as us-states.csv that contains USA State Level COVID-19 cases and deaths 
from 2020 to 2022.

### Package Used
The project was running using the Jupyter notebook console 6.4. Pandas, numpy, plotly, 
matplotlib, statsmodels, sklearn and pmdarima were used as packages.

### Explaratory Data Analysis
#### Cases and Death in USA
![Figure 2](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%202.png?raw=true)

#### Cases and Fatality Of Each State
![Figure 3](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%203.png?raw=true)

#### USA Daily New Cases
![Figure 4](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%204.png?raw=true)

### ETS Decomposition for the USA Dataset

Decomposition of time series is a statistical activity in which a time series is broken 
down into numerous components, each representing one of the underlying groups of patterns.

This is a crucial strategy for all forms of time series analysis, particularly seasonal adjustment. 
It aims to create several component series (that could be used to reconstruct the original by 
additions or multiplications) from an observed time series, each of which has a distinct 
characteristic or type of behavior. Time series, for example, are frequently split into:
- Tt, the trend component at time t, which indicates the series' long-term evolution 
(secular variation). When data has a consistent increasing or declining tendency, it is 
called a trend. It is not necessary for the trend component to be linear.
- Ct, the cyclical component at time t, which reflects non-periodic fluctuations that occur 
again. The length of these variations is determined by the time series' nature.
- St, the seasonal component, reflects seasonality (seasonal variation). When seasonal 
influences influence a time series, a seasonal pattern emerges. Seasonality occurs over 
a set and predictable time span (e.g., the quarter of the year, the month, or day of the 
week).
- It expresses random, irregular influences as the irregular component (or "noise") at time 
t. After the other components have been removed, it reflects the residuals or remainder 
of the time series.

Hence a time series using an additive model can be thought of as

Yt = Tt + Ct + St + It

whereas a multiplicative model would be

Yt = Tt × Ct × St × It

Here we see that the seasonal component does not contribute significantly to the behavior of 
the series.

![Figure 5](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%205.png?raw=true)

### Augmented Dicky Fuller Test
In time series, the data must be stationary for analysis. The statistical features of a time 
series, such as mean, variance, and covariance, are stationary if they remain constant across 
time. Plotting the data and performing a visual analysis, as well as using a statistical test, are 
formal approaches to verify for this.
Visually, we can use the decomposition approach to display seasonality (which might be daily, 
weekly, monthly, etc.), trend, and random, which is the variability in the data set after the 
effects of seasonality and trend have been removed.
Statistical test: We will apply the Dickey-Fuller Hypothesis testing to confirm our eye 
observation on the given figure. Dickey Fuller test tests the null hypothesis that a unit root is 
present in an autoregressive time series model. Result is shown in Figure 2.5.

Null Hypothesis: The series is not stationary.
Alternate Hypothesis: The series is stationary.

![Figure 6](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%206.png?raw=true)

With the p-value 0.997464 which is greater than 0.05, we fail to reject the null hypothesis & 
it confirms that the series is not stationary.

###  Kwiatkowski-Phillips-Schmidt-Shin (KPSS) Test
The KPSS test, short for Kwiatkowski-Phillips-Schmidt-Shin (KPSS), is a sort of Unit root test 
that determines if a given series is stationary around a deterministic trend.
The null hypothesis of the KPSS test is that the series is stationary, which is a key difference 
from the ADF test.

So, in practise, p-value interpretation is the polar opposite of each other.
That is, if the p-value is greater than the significance level (for example, 0.05), the series is 
non-stationary. In the ADF test, however, it means the tested series is stationary.
The following assumptions are used to conduct the KPSS test.
Null Hypothesis (HO): Series is trend stationary, or series has no unit root.
Alternate Hypothesis(HA): Series is non-stationary or series has a unit root.
Note: Hypothesis is reversed in KPSS test compared to ADF Test.
If the null hypothesis is failed to be rejected, this test may provide evidence that the series is 
trend stationary.

Conditions to Fail to Reject Null Hypothesis(HO)

If Test statistic < Critical Value and p-value < 0.05 – Fail to Reject Null Hypothesis(HO) 
i.e., time series does not have a unit root, meaning it is trend stationary.

![Figure 7](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%207.png?raw=true)

Since the test statistic 4.09 > Critical Value 0.463 and p-value 0.010 < 0.05. As a result, we 
reject the Null hypothesis in favour of an Alternative.

## Result & Discussion
### Differencing
A Time Series is said to be stationary if its statistical properties such as mean, variance remain 
constant over time. 
This is significant since most Time Series models assume that the Time Series is stationary. 
Intuitively, we may say that if a Time Series exhibits a certain pattern throughout time, there 
is a very good chance that it will continue to do so in the future. In addition, compared to nonstationary series, stationary series theories are more developed and easier to apply. Stationarity 
is defined by a stringent set of criteria. To assume that the time series to be stationary if it has 
constant statistical properties over time as following:

- constant mean
- constant variance
- an autocovariance that is not time dependent

Therefore, we must make the series stationary and determine the d value once the statistical 
test confirms that it is not stationary. We can accomplish this by removing the trend and 
bringing the series to a stationary. Differencing is one of the most frequent ways for removing 
both the trend and seasonality, and the d value represents the number of times the differencing 
was conducted to make the series stationary.

Using Differencing 1 result are shown as below. The ADF test still show the series are still not 
stationary.

![Figure 8](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%208.png?raw=true)

We then run again the Differencing 2 on the data and get the stationary result.

![Figure 9](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%209.png?raw=true)

We repeat the same process for KPSS test and we able to confirm the same, the series will be 
stationary after 2 times differencing.

![Figure 10](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%2010.png?raw=true)

As a result, after two times differencing, we can validate that the series will be stationary 
and fit for our time series analysis.

### ACF and PACF Graph

The Partial Autocorrelation Function (PACF) determines a time series' partial correlation with 
its own lagged values while adjusting for the time series' values at all shorter lags. The 
Autocorrelation Function calculates the correlation of a time series based on its own lagged 
values, but without considering the other lags.

The ACF plot for the AR(p) time series would be strong up to a lag of p and then remain static 
for future lag values, falling off at some point as the influence weakens. On the other hand, the 
PACF describes the direct relationship between an observation and its lag. For lag values 
greater than p, this usually results in no connection.

The MA(q) process' ACF would show a substantial correlation with recent values up to q's lag, 
then a rapid drop to minimal or no correlation. The plot for the PACF indicates a robust 
association up to the lag, then a drop to no correlation after that. The ACF and PACF plots for 
our stationary data are shown below.

![Figure 11](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%2011.png?raw=true)

ACF graph shows that the series is decaying towards time at 300 lags and PACF plot 
shows that the series is significant at lag 2. 

### Auto ARIMA Stepwise Order

Auto ARIMA model: The advantage of using Auto ARIMA over the ARIMA model is that 
after data pre-processing step we can skip the next steps & directly fit our model. It uses the 
AIC (Akaike Information Criterion) & BIC (Bayesian Information Criterion) values generated 
by trying different combinations of p, q & d values to fit the model.

Using the Auto ARIMA stepwise order it’ll be easy to gain the best result to forecast the model. 
Figure below showcase the Auto ARIMA running to gain the best result from AIC to determine 
the best order.

![Figure 12](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%2012.png?raw=true)

![Figure 13](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%2013.png?raw=true)

Based on the Auto ARIMA the best order to fit into the ARIMA forecasting model is 
ARIMA(3,2,3). It’s the best model to forecast future values of the series.

### ARIMA
A time series is a collection of data points collected at regular intervals of time, such as 
yearly, daily, monthly, hourly, and so on. It is time-dependent, and the passage of time is a key 
feature of the data collection. The ARIMA model, which stands for Auto Regressive Integrated 
Moving Average, is one of the most commonly used time series forecasting models. ARIMA 
is a model that may be used to forecast future points in a time series by fitting it to the data.

The Arima word can be broken down into three parts: AR, I, and MA:

The p parameter confirms how many lagged series will be used to predict periods ahead. AR(p) 
stands for autoregressive model, and the p parameter is an integer that verifies how many 
lagged series will be used to forecast periods ahead.

The d parameter specifies how many differencing orders will be utilized to make the series 
stationary. I(d) is the differencing portion.

MA(q), where q is the number of lagged forecast error terms in the prediction equation, stands 
for moving average model. Seasonal ARIMA (SARIMA) is a method for analyzing time series 
with seasonality.

### Building ARIMA Model
![Figure 14](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%2014.png?raw=true)
The ARIMA model is built with 50 days as a test using the order provided by the Auto ARIMA 
stepwise order, which is ARIMA (3,2,3), which has close to 16K AIC values.

Plotting of the tested build ARIMA model showcase the result as below. Cases is colored in 
blue and the prediction using ARIMA(3,2,3) is colored in orange.

![Figure 15](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%2015.png?raw=true)

Plotting the tested ARIMA model to full forecast plot, we can see the forecast in the 95% 
confidence interval band or colored. This result in a good forecast. Figure below displays the 
full forecast plot.

![Figure 16](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%2016.png?raw=true)

### Evaluation Metrics
![Figure 17](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%2017.png?raw=true)

Using the error rate for evaluation metrics. Based on the figure, test data error rate is 5989188. 
And the mean for test data is 55313198. The error rate gained is 0.10828.

### Full Forecasting Result
![Figure 18](https://github.com/Vu5e/ForecastingCov19ARIMA/blob/main/Image/Image%2018.png?raw=true)

With the error rate gained of 0.10828, the forecast value is inside the confidence 
interval, which means it is still a good model by using the full data retrained and forecasted. 
But the confidence interval is not as big as the 50-day test, which means for a long-time 
interval, it is not a good model. But for ARIMA, a short interval is better suited to it.

## Conclusion
In this study, we have proved that time series with auto-ARMA stepwise were able to 
predict the future cases of COVID-19 cases in the USA. However, to make sure that we can 
run ARIMA on the series, we must make sure that the series is stationary. The characteristics 
of a stationary time series mean that the series does not depend on time, does not have a trend, 
or does not have a seasonal effect. We can use tests like the Augmented Dickey Fuller Test and 
the Kwiatkowski-Phillips-Schmidt-Shin (KPSS) Test to see if the series is stationary and fits 
the time series characteristic. On the augmented Dicky Fuller Test with a p-value of 0.997464 
(which is greater than 0.05), we fail to reject the null hypothesis and confirm that the series is 
not stationary. The Kwiatkowski-Phillips-Schmidt-Shin (KPSS) Test also shows the same, and 
we reject the null hypothesis in favor of an alternative. Because both tests confirmed that the 
series is not stationary, we must apply differencing. Differencing is where a previous 
observation is subtracted from the current observation. Differencing can also remove trends 
and seasonality. Once the series is stationary, we can now apply the ARIMA time series. 
Aside from that, epidemics are frequently significantly more complex than we realize, and 
many other factors, such as vaccine production efficiency, population vaccination rates, virus 
changes, and so on, affect the model's accuracy. The new coronavirus, Omicron, for example, 
was recently found in South Africa. According to data given by South Africa's National Agency 
for Communicable Diseases, Omicron was discovered in 74% of the country's 249 confirmed 
coronavirus samples. According to the nation, Omicron has quickly surpassed Delta as the 
major coronavirus in South Africa. We need to add more variables and tweak the algorithm to 
better anticipate the number of diagnoses. At the same time, I am confident that, with the 
passage of time and technological advancement, humanity will finally conquer the plague and 
return to normal life!

## Acknowledgements
We would like to thank our fellow classmates from CS779 who helped with the project; 
without them, we would not have been able to complete this project and without them we would 
not have made it through our master’s degree. Also, special appreciation to STA768 Dr. 
Meriam, lecturer, for her effort to keep teaching the killer subject, Time Series Analysis.

## References
Cucinotta, D., & Vanelli, M. (2020). WHO declares COVID-19 a pandemic. Acta Biomedica, 91(1), 
157–160. https://doi.org/10.23750/abm.v91i1.9397
Holshue, M. L., DeBolt, C., Lindquist, S., Lofy, K. H., Wiesman, J., Bruce, H., Spitters, C., Ericson, 
K., Wilkerson, S., Tural, A., Diaz, G., Cohn, A., Fox, L., Patel, A., Gerber, S. I., Kim, L., Tong, 
S., Lu, X., Lindstrom, S., … Pillai, S. K. (2020). First Case of 2019 Novel Coronavirus in the 
United States. New England Journal of Medicine, 382(10), 929–936. 
https://doi.org/10.1056/nejmoa2001191
Perlman, S. (2020). Another Decade, Another Coronavirus. New England Journal of Medicine, 
382(8), 760–762. https://doi.org/10.1056/nejme2001126
Wang, M., Cao, R., Zhang, L., Yang, X., Liu, J., Xu, M., Shi, Z., Hu, Z., Zhong, W., & Xiao, G. 
(2020). Remdesivir and chloroquine effectively inhibit the recently emerged novel coronavirus 
(2019-nCoV) in vitro. Cell Research, 30(3), 269–271. https://doi.org/10.1038/s41422-020-0282-
0
Zhu, N., Zhang, D., Wang, W., Li, X., Yang, B., Song, J., Zhao, X., Huang, B., Shi, W., Lu, R., Niu, 
P., Zhan, F., Ma, X., Wang, D., Xu, W., Wu, G., Gao, G. F., & Tan, W. (2020). A Novel 
Coronavirus from Patients with Pneumonia in China, 2019. New England Journal of Medicine, 
382(8), 727–733. https://doi.org/10.1056/nejmoa2001017
Darapaneni, N., Reddy, D., Paduri, A. R., Acharya, P., & Nithin, H. S. (2020). Forecasting of 
COVID-19 in India Using ARIMA Model. 2020 11th IEEE Annual Ubiquitous
Computing, Electronics and Mobile Communication Conference, UEMCON 2020. 
https://doi.org/10.1109/UEMCON51285.2020.9298045
