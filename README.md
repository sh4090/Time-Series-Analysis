# Time-Series-Analysis

### Project Overview 
In this project, I developed a time series model in R to explore the factors contributing to the increasing representation of women in Moroccan politics between 1990 and 2021. The analysis involved multiple socio-economic variables extracted from World Bank data and the V-dem Institute, including:

- Parliamentary Seats held by Women (pr)
- Female Labor Force Participation (lfpr)
- Fertility Rate (rate)
- Gross National Income per Capita of Women (gnipc)
- Expected Years of Schooling (eys)
- Foreign Direct Investment (fdi)
- GDP Growth Rate (growth)
- Freedom of Expression (exp)

The code uses multiple R packages, including tidyverse, ggplot2, ggcorrplot, forecast and car.
The following only goes over some of the methodology used. For a more detailed quantitative analysis, please visit my paper (https://drive.google.com/file/d/18fbNUzXj9ro3SJ_FZsYenuKXMGjUJ1WM/view?usp=sharing).

### Statistical Tools and Models
The code includes the following statistical tools:
- Correlation matrix
- Linear Regression Model (OLS)
- AutoCorrelation Function (ACF) to check for serial correlation and stationarity, graphically
- Durbin-Watson test to check for autocorrelation in OLS model
- Dicky-Fueller test to check for cointegration
- Prais-Winsten regression to correct for autocorrelation in OLS model
- Difference in Differences model (DiD)

### Project Steps

#### Cleaning and Transformation:
- Utilized World Bank data and various country-specific indicators.
- Filtered, merged, and transformed datasets into time series format in R, ensuring a consistent temporal range for analysis.

#### Descriptive and Exploratory Analysis:
- Conducted visualizations to plot variable trends over time using ggplot2, highlighting key economic and social changes.
- Created summary statistics and a correlation matrix to explore relationships between variables.

#### Modeling:
- Implemented an OLS regression model to identify significant predictors of women's representation in parliament.
- Diagnosed serial correlation using the Durbin-Watson test, revealing autocorrelation.
- Applied techniques to test for non-stationarity using the Augmented Dickey-Fuller test and autocorrelation function (ACF).
- Corrected OLS model using Prais-Winsten regression.
- Substituted model for a Difference in Differences model because of continued autocorrelation problem and an abnormally high R².

### Overall Findings
It was hard to make any conclusion with regards to my initial theory as to the factors contributing to increased female political participation in Moroccan politics. This comes despite corrections and mitigation of autocorrelation, non-stationarity and cointegration. I was not able to produce a meaningful model because of the high correlation between the variables of the OLS model. The Difference in Differences model does seem to give some legitimacy to the theory in terms of impact over time, but with no statistical significance. 

#### Possible alternative
It seems as though the only way to make sure of the relevance of the model is by the introduction of interaction terms between the independent variables. However, given the large number of variables, this would make the model too complex. An alternative solution would be to split the variables into multiple models so as to simplify the individual models but still be able to investigate the factors contributing to the increase in women’s representation in Moroccan politics. This would increase Type I and Type II error, given the increase in the number of models, however, it could still yield interesting findings for political science despite not being ideal from a statistics point of view.

