# PSTAT 174 Data Report
 This repository contains my Time-Series Data Project I created for **PSTAT 174** when I was a student at UCSB. The final product was developed over the course of one month *(from 5/11/23 to 6/13/23 or the Spring 2023 semester)*, where it was then presented in front of an audience. The main goal of the project was to apply time-series concepts learned in class to real world data. For my case, I choose to examine the widely traded currency pair of USD to JPY, and tried to predict the exchange rate 12 months out.

## Project Description
 The USD to JPY currency trade is the third most popular exchange rate in the world. Although exchange rates are heavily influenced by real world events and respective government policies, the exchange is ultimately a time-series upon which we apply can apply concepts and models to. This project aims to fit two different types of time-series models, SARIMA and GARCH, to forecast twelve monthly points of the exchange rate.   

 My methodology was hypothesising that the USD to JPY exchange rate was a seasonal time-series, and that it can be expressed as a non-complex **SARIMA** *(Seasonal AutoRegressive Integrated Moving Average)* model. It is generally regarded that financial tickers, such as stocks, have seasonal tendencies in which they perform better or worse. One well known example is the S&P 500, where it has been observed that the S&P 500 has noticeably **lower returns in the months January, June and September** over a twenty year average. Conversely, the S&P 500 also **performed better in April, July, and November** in that same twenty year average. 
 
 If financial tickers did not have a seasonal component to them, then there should not be strong or weak months, but instead a consistent return rate for all months. This is not the case, so the S&P 500 has seasonal trends. Using the same line of logic, I applied this hypothesis to the currency pair. For selecting data, I took the first reported closing exchange rate of each month to be my data points. For missing data points, I copied the previous days' closing price since the actual difference would be miniscule. This way, the data would be uniform and accepted as a time series in the code.

 Additionally, financial tickers all have some skew of erratic behavior to them. In hopes to capture that movement, I elected to run the **GARCH** *(Generalized AutoRegressive Conditional Heteroskedasticity)* model alongside the SARIMA model. Once each model reported the best fitting parameters, I forecasted the next twelve months from the last data point and concluded my results.

## Project Download
 Accessing the project's code requires R (4.3) and RStudio (IDE) to view. R can be downloaded from their homepage: https://cran.r-project.org/ and RStudio likewise: https://posit.co/. Additionally, this project uses packages to convert dates to be time-series friendly and introduce framework of ts models. The packages used in this project are: 

| Package  | Purpose |
| ------------- | ------------- |
| **knitr**  | Used for tables/plots in pdf form |
|  **quantmod** |  Used to pull financial data from Yahoo Finance |
| **tidyr**  | Used to strip redundant information from Yahoo Finance data  |
|  **lubridate** | Used to convert dates into an easier form to work with  |
|  **xts** |  Converts a string of dates to be recognized as a time-series |
|  **astsa** |  Allows for analysis of time-series, i.e. ARIMA modeling |
|  **timetk** |   Allows forecast plots for time series models|
|  **fGarch** |  Provides support for the GARCH model |


 If you are viewing this on a device unable to run R, a pdf is also provided, organizing all findings in a research paper format. The code is included in the appendix of the pdf. The project's plots are also included in a separate folder labeled 'Plots' for better resolution/viewing.

## Disclaimer
 This project is for the purposes of demonstrating how the USD to JPY exchange rate is a time series and how one would implement it. This is clearly evident from the final product being stylized as a data report covering the background of the exchange and my own findings. This data report IS NOT FINANCIAL ADVICE nor should it be interpreted as such. You should not use the predicted forecast as an indicator to buy or sell the currency pair. I am not a financial advisor, I am just a student showing a proof of concept. 

 If you are a student that is taking PSTAT 174, please do not copy/plagarize my work. Feel free to look at the processes used and derive your own project, but don't just copy the code directly in.

# Credits
  This was a solo project implemented by me, Alexander Carbone. All time-series concepts and advisory came from Professor Tomoyuki Ichiba's Spring 2023, PSTAT 174 TIME SERIES course at the University of California, Santa Barbara. Thank you Professor for teaching a fun course and allowing me to produce a project on these concepts. The financial data of the USD to JPY exchange rate was pulled from Yahoo Finance under the ticker **"JPY=X"** and financial data belongs to them.
