# King County House Pricing Project 
![image (1)](https://github.com/ericwambua/dsc-phase-2-project-v2-3/assets/133090475/33cf5ce0-532d-4538-a209-584aa5e0fb10)
## Project Overview

This project focuses on providing data-driven insights to real estate firms operating in King County. Leveraging a comprehensive dataset containing various housing-related features and house prices, the goal is to gain a deep understanding of the factors influencing house prices in the county. This information will enable real estate professionals to make informed decisions, enhance their property valuation processes, and optimize their market strategies.
### Business Problem

The King County housing market exhibits various patterns and factors influencing house prices. However, there is a need to understand these factors more comprehensively to aid real estate stakeholders in making informed decisions. The primary business problem is to develop a robust pricing model that accurately predicts house prices based on various features. This model should provide insights into which features have the most significant impact on house prices and help real estate professionals, sellers, and buyers make informed decisions.

### Project Objectives:
The project aim is to construct a predictive model for house prices in King County, Washington, utilizing comprehensive data encompassing bedrooms, bathrooms, square footage, condition, location, and relevant attributes. This endeavor serves a dual purpose: understanding the primary determinants of house prices and enhancing pricing accuracy for real estate transactions.

### The Data

• We utilized the King County House Sales dataset, 
which comprises various house features including 
bedrooms,  bathrooms,  square  footage,  views, 
and ZIP codes,  as influential factors on house 
prices.
• We  analyzed  these  features  to  predict  house 
prices and provide valuable insights for sale price 
predictions. These insights can be beneficial for 
stakeholders  such  as  real  estate  agents  in 
advising their clients.

### Column Descriptions
* id - Unique identifier for a house
* date - Date house was sold
* price - Sale price (prediction target)
* bedrooms - Number of bedrooms
* bathrooms - Number of bathrooms
* sqft_living - Square footage of living space in the home
* sqft_lot - Square footage of the lot
* floors - Number of floors (levels) in house
* waterfront - Whether the house is on a waterfront
* view - Quality of view from house
* condition - How good the overall condition of the house is. Related to maintenance of house.
* grade - Overall grade of the house. Related to the construction and design of the house.
* sqft_above - Square footage of house apart from basement
* sqft_basement - Square footage of the basement
* yr_built - Year when house was built
* yr_renovated - Year when house was renovated
* zipcode - ZIP Code used by the United States Postal Service
* lat - Latitude coordinate
* long - Longitude coordinate
* sqft_living15 - The square footage of interior housing living space for the nearest 15 neighbors
* sqft_lot15 - The square footage of the land lots of the nearest 15 neighbors

### Methodology:
The project follows a structured methodology to achieve its objectives:

* Data Preprocessing: Loading and cleaning the dataset, tackling issues such as missing values, outliers, and categorical variables. Ensuring data quality is essential for reliable analysis.

* Exploratory Data Analysis (EDA): Comprehensive EDA is conducted to gain insights into the data's distribution, correlations, and patterns. Visualizations and statistical analyses are employed to uncover significant trends.

* Feature Selection: Through correlation analysis, VIF assessment for multicollinearity detection, and domain knowledge, significant features are identified. This step is crucial in determining which aspects of a property have the most substantial impact on house prices.
  
* Model Building: Multiple regression models, including linear, multiple linear, and advanced techniques, are constructed to predict house prices. These models leverage the identified features to provide accurate estimates.
  
* Model Evaluation: Model performance is assessed using metrics such as R-squared, p-values, and feature coefficients. Continuous evaluation ensures the model's reliability.

* Model Optimization: Fine-tuning the model is essential to enhance predictive accuracy and interpretability, making it a valuable tool for decision-making.

### Data Processing
We conducted data cleaning on the dataset, addressing issues such as duplicate entries and missing values. To handle missing data, we employed imputation techniques. Categorical variables were transformed using one-hot encoding, and we also performed feature engineering on select variables to enhance the dataset's predictive power

### Exploratory Data Analysis (EDA)
The  majority  of  homes  in  our dataset have between 2 and 5 bedrooms,  0.5  to  3  bathrooms  and 1 and 2 floors

![Distributions](https://github.com/ericwambua/dsc-phase-2-project-v2-3/assets/133090475/09a55fa6-f460-40ff-a8f2-4060c12d3fff)


The  dataset  is  predominantly composed  of  houses  that  are  not on  a  waterfront  and  lack  scenic views. Most  of  these  houses  are  in moderate  condition,  with  grades typically  ranging  from  average  to good,  and  renovations  are infrequently observed. 

![waterfront](https://github.com/ericwambua/dsc-phase-2-project-v2-3/assets/133090475/bfa58287-0e5f-44dd-834e-2d564890556e)



The number of bedrooms and bathrooms  directly  affects house prices. Houses with 2.5 floors tend to be  the  most  expensive  on average.

![averagePrice](https://github.com/ericwambua/dsc-phase-2-project-v2-3/assets/133090475/00ee2da6-1eff-4168-84a0-c59b44b98326)

While  seasonality  does  not significantly impact prices, sellers may still benefit from listing their properties during  the  spring  and  summer seasons  when  demand  tends  to  be higher.

![SalesSeason](https://github.com/ericwambua/dsc-phase-2-project-v2-3/assets/133090475/bae61ec9-346a-48c9-98d5-a790ec6c164f)


The analysis highlights the importance of considering location, as specific zipcodes exhibit variations in average property prices
![PriceZipcode](https://github.com/ericwambua/dsc-phase-2-project-v2-3/assets/133090475/852aace6-0a7d-4d55-977c-43c7234a46bc)

### Testing for Multicollinearity
VIF(Variance Inflation Factor) is a measure to detect multicollinearity in regression.
After reviewing the correlation matrices, we identified significant positive correlations among our independent variables. Consequently, we have decided to conduct a multicollinearity test before proceeding with our regression analysis.
* "bedrooms" "bathrooms" "sqft_living" "sqft_above" and "sqft_basement" have VIF values equal to infinity, indicating high multicollinearity. 
* Features with VIF values between 1 and 5, such as "grade," "sqft_living15," "sqft_lot15," "month," and "sale_season," indicate moderate multicollinearity. 
* Features with VIF values less than 1, such as "floors," "waterfront," "view," "condition," "zipcode," "renovated," and "basement," do not exhibit substantial multicollinearity.

### Model Building and Evaluation
SIMPLE LINEAR REGRESSION RESULTS
There  is  a  strong  positive correlation  between  price  and sqft_living.For each additional square foot of living  space,  the  price  increases by about $282. 18.


![model1](https://github.com/ericwambua/dsc-phase-2-project-v2-3/assets/133090475/17708d17-692d-4f0b-aa51-383d4dc5d493)


#### MULTIPLE LINEAR REGRESSION RESULTS
* The first model focused on highly correlated  variables  with  price; 'bathrooms',  'grade', 'sqft_living15',' sqft_living', 'view', 'bedrooms'.
 The model explains 0.57  of the variance price.
* We progressively included more variables until we identified the model with the highest R-squared value, which resulted in the following model.
* The  final  model  utilized  our previous  findings  and  domain knowledge.The  independent  variables  included; 'sqft_lot',  'floors',  'waterfront',  'view', 'condition',  'grade',  'yr_built', 'sqft_living15',  'sqft_lot15',  'renovated', sqft_living', 'basement', 'bedrooms'.The  model  explains  0.65  of  the variance in price.

![model2](https://github.com/ericwambua/dsc-phase-2-project-v2-3/assets/133090475/54d2c90a-0dcb-454e-8f20-7e73fc04ce1b)


### Study Limitations
* Our analysis recognizes the limitations stemming from the absence 
of several critical factors in our dataset, which can substantially 
influence  house  prices.  Consequently,  our  model's  predictive 
accuracy was constrained, achieving a rate of 65%. 
* Notable  missing  data  include  Geospatial  Data,  Location,  Market 
Trends, Amenities, Local Infrastructure,  Property Attributes, Market 
Dynamics, Property History, Zoning Regulations among others

### Recommendations
* Develop a Data-Driven Pricing Strategy.
* Promote Unique Features, such as waterfront views, through 
targeted marketing to attract premium-paying buyers.
* Location-Based Marketing.
* Adapt sales and marketing strategies to align with seasonal 
trends.
* Data-Driven Decision Making
### Conclusion
* Spring  and  summer  listing  may  benefit  sellers  due  to  increased 
demand.
* Zipcodes' findings underline the importance of location in pricing. 
* Scenic settings, such as waterfront views, command a substantial 
premium.
* Take caution on the multicollinearity of features as it can affect pricing 
model accuracy. 
* Possible  predictive  model  limitations  due  to  missing  factors  e.g., 
market trends, amenities, economic factors, and more, all influencing house prices






