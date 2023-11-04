# Housing Price Prediction Model

# Introduction
The housing market is a critical pillar of the United States economy, accounting for 15-18% of GDP. However, it is also highly complex with prices determined by an intricate interplay of factors like demand-supply dynamics, affordability, interest rates and availability of credit. The Great Recession of 2008 revealed the vulnerabilities of the housing sector, causing immense financial distress. Since then, the market has made a recovery with median home prices rising 31% between 2012-2022.
However, new challenges have emerged with inflated property valuations and unaffordability. This underscores the need for data-driven insights and predictive analytics in real estate. Reliable valuation models can greatly aid agencies and individuals make prudent investment decisions. This project aims to leverage housing data analytics to unravel pricing patterns in King County, Washington. The model developed here attempts to statistically estimate property values based on intrinsic attributes like square footage, bedrooms and location.

# Project Overview
This project involved developing a multivariate linear regression model to predict housing prices in King County, Washington based on features like square footage, number of bedrooms/bathrooms, and overall condition. The model aims to help real estate agencies estimate property values.
The dataset contained information on 21,597 houses sold between May 2014 - May 2015 sourced from the King Country House Dataset.

## Data Cleaning and Preprocessing
The raw data underwent cleaning and preprocessing:
<ul>
<li> Dropped irrelevant columns like id, sqft_above, sqft_basement etc.</li>
<li> Handled missing values by dropping rows</li>
<li> Removed outliers using interquartile range</li>
<li> Encoded categorical variables like condition and grade numerically</li>
<li> Added neighborhood data by merging datasets</li>
<li> Added seasonality feature by extracting month from date</li>
</ul>

# Business Understanding
The key stakeholders for this project are real estate agencies and their clients in King County, Washington. Real estate is a complex industry with property prices dependent on several dynamic factors. Determining fair valuations is critical yet challenging. This project aims to develop a data-driven model that can analyze past sales data to predict prices of houses based on intrinsic attributes like size, bedrooms, location etc.
The model will help real estate agents provide more accurate price estimates to clients for buying/selling houses. It will also aid clients make better investment decisions when purchasing properties. Additionally, insights from the model can help agencies formulate effective pricing and marketing strategies by identifying the most influential factors. For instance, the model may reveal that an additional bathroom adds more value than an extra bedroom.
By leveraging such data analytics, real estate firms can gain a competitive edge with enhanced price modelling capabilities. Overall, this project focuses on using King County housing data to create a regression model that can explain and predict property valuations.

# Data Understanding
The core dataset for this project is the King County House Sales dataset from 2014-2015. It contains 21,597 rows and 21 columns of housing data like sale price, square footage, number of bedrooms/bathrooms, location coordinates etc. 
Key highlights: 
<ul>
<li>Source: University of Chicago's Center for Spatial Data Science</li>
<li>Time period: May 2014 - May 2015</li>
<li>Format: CSV file </li>
<li>Rows: 21,597 </li>
<li>Columns: 21 (sale price, bedrooms, bathrooms, sqft, location, date etc.)</li>
<li>Data types: Numeric (integers, floats) and categorical strings </li>
<li>Null values present in some columns like waterfront, view etc. which were dropped. Supplemented with additional neighborhood data by merging two datasets Engineered new feature for seasonality by extracting month from sale date.</li>
</ul>
The data understanding phase focused on initial exploration of the dataset to determine properties like size, structure, distributions, data types, null values and outliers. This formed the foundation for subsequent cleaning, preprocessing and modelling work.

# Modeling
## Baseline Model
A simple linear regression model was created with 'price' as the target variable and 'sqft_living' (square footage) as the only predictor. This baseline model had an R-squared of 0.384, indicating sqft_living alone explained 38.4% of variance in price.

## Multivariate Model
A multivariate linear regression model was built by adding more predictors - bedrooms, bathrooms, condition. The R-squared improved to 0.403 with the additional variables, explaining 40.3% of variance.

### Model Evaluation
Both models were statistically significant with p<0.05. The multivariate model was assessed for linear regression assumptions like linearity, normality, homoscedasticity. Residual analysis was performed to check for independence and normal distribution.
In summary, a simple model was created first, then a multivariate model with more predictors improved the R-squared and predictive capability though still far from perfect.

## Results and Findings
A multivariate linear regression model was developed with price as the target variable and sqft_living, bedrooms, bathrooms and condition as the predictors.
The final model had an R-squared of 0.403, indicating it explains 40.3% of the variance in house prices. All the independent variables were statistically significant with p-values < 0.05.
Each additional bathroom was associated with a $15,990 increase in predicted price, holding other factors constant. Every extra square foot of living space added approximately $176 to the predicted price, ceteris paribus. An additional bedroom was linked to a $26,770 decrease in predicted price, all else being equal. Improving the condition rating by 1 grade added around $30,560 to the predicted price on average.
Positive correlations were observed between price and sqft_living, bathrooms, condition while bedrooms had a negative correlation. The model met the assumptions of linear regression like linearity, independence, homoscedasticity and normality of residuals.
In summary, the size, bathrooms and condition had positive effects on price while more bedrooms lowered predicted prices, per the model on this dataset. These insights can help guide pricing and investment decisions.

# Conclusion
The linear regression model developed in this project explains approximately 40.3% of the variation in house prices based on features like square footage, bedrooms, bathrooms and condition. While not completely accurate, it provides a reasonably good fit. Key factors positively impacting predicted prices are size of living space, number of bathrooms and overall condition. More bedrooms negatively affect price. This indicates what home aspects to prioritize when buying, selling or renovating. However, numerous other attributes influence property values like location, amenities, economic conditions etc. So the model should be enhanced by incorporating additional relevant variables. For reliable real-world application, the model needs refinement with extra data. But it serves as a useful starting point for agencies to estimate prices and guide strategy. Overall, this project demonstrates the potential of applying data analytics in real estate to uncover pricing patterns and dynamics. The methods can be extended to build superior valuation models by leveraging more granular housing data.


# Recommendations
1.	The size of the living space, as represented by the 'Sqft_living' variable, is a significant driver of house prices. If possible, consider focusing on properties with more substantial living spaces, as they tend to command higher prices.
2.	While an increase in the number of bedrooms is associated with a reduction in price in your model. However, this should be investigated further. It might be specific to the dataset or region you're working with.
3.	The condition of a house significantly impacts its price. If you're looking to sell or invest in properties, it's worthwhile to maintain or improve their condition to increase their market value.
4.	From our analysis it was found that the number of bathrooms positively correlates with the house prices we recommend that our stakeholder puts more investment/consideration of this factor be it in the buying, selling or even renovation of houses.
5.	Our analysis proves that location is also a huge factor that affects appreciation or depreciation of house prices. Real estate agents should therefore consider the neighborhood when advising their clients on the property to invest in. In particular, the agents should look out for the safety of the neighborhoods, proximity to key amenities such as hospitals and schools, as well as the affluency of a location when determining the price levels.

# Next Steps
Conducting additional analysis to pinpoint the factors that are influencing the model's predictions would be beneficial to explore the inclusion of new variables that could enhance the model's accuracy, for example crime data by zip code, school rating data as well as data regarding other social amenities.
