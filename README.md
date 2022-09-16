<h1 align='center'>House Prices Advanced Regression Techniques</h1>

The work performed here is based on data from the Kaggle competition below:
https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques

## Table of Contents
<details open>
<summary>Show/Hide</summary>
<br>

1. [ Business Problem ](#TESTEST)
<!-- 2. [ Technologies Used ](#Technologies_Used)    
3. [ Structure ](#Structure)
4. [ Executive Summary ](#Executive_Summary)
   * [ 1. Webscraping, Early EDA, and Cleaning ](#Webscraping_Early_EDA_and_Cleaning)
       * [ Webscraping ](#Webscraping)
       * [ Early EDA and Cleaning](#Early_EDA_and_Cleaning)
   * [ 2. Further EDA and Preprocessing ](#Further_EDA_and_Preprocessing) 
   * [ 3. Modelling and Hyperparameter Tuning ](#Modelling)
   * [ 4. Evaluation ](#Evaluation)
       * [ Future Improvements ](#Future_Improvements)
   * [ 5. Neural Network Modelling ](#Neural_Network_Modelling)
   * [ 6. Revaluation and Deployment ](#Revaluation) -->
</details>


### Business Problem

As a business, it is difficult to assess the appropriate value for homes in certain neighborhoods/markets. There is a need for more precision and confidence in valuation to support decision-making. Developing a data-driven / model-based approach to valuation can help to remove human bias.

As a building developer, it is difficult to weigh the importance of attributes to potential home buyers. A model-based approach can help assess what factors drive the overall value of a home.

Inference Problem

X: 79 explanatory variables describing aspects of residential homes in Ames, Iowa
y: Home price

Develop a model to predict home price based on a collection of attributes about the home and surrounding neighborhood.

Methodology

Exploratory data analysis
Use pandas profiling minimal for overview
Develop calculated metrics using numerical variables
Apply one-hot encoding to relevant ordinal variables
Model setup
Set of regression models
Basic Linear Regression
Comprehensive Linear Regression
Suite of advanced models
Model evaluation and iteration
Evaluate performance metrics: 𝑅2, MSE, MAE, RMSE
Error analysis - residuals
Assess feature importance, apply dimensionality reduction
Determine which models to exclude, features to exclude/include/adjust
Repeat model setup
Background Research
How Zillow calculates home price

Zillow publishes Zestimate home valuations for 104 million homes across the country, and uses state of the art statistical and machine learning models that can examine hundreds of data points for each individual home.

To calculate a Zestimate, Zillow uses a sophisticated neural network-based model that incorporates data from county and tax assessor records and direct feeds from hundreds of multiple listing services and brokerages. The Zestimate also incorporates:

Home characteristics including square footage, location or the number of bathrooms.
On-market data such as listing price, description, comparable homes in the area and days on the market
Off-market data — tax assessments, prior sales and other publicly available records
Market trends, including seasonal changes in demand
Currently, we have data for over 110 million U.S. homes and we publish Zestimates for 104 million of them.

https://www.zillow.com/research/zestimate-forecast-methodology/

From learning about how Zillow, we could try a neural network-based model, although we might not have enough data. We are provided with solely home characteristics for this project, and it seems like square footage, location, and the number of bathrooms are notable features we should include in our final model.

Opendoor article on factors that influence home value

Most important factors:

Neighborhood comps
Location
Home size and usable space
Age and condition
Upgrades and updates
The local market
Economic indicators
Interest rates
https://www.opendoor.com/w/blog/factors-that-influence-home-value

Based on the Opendoor article, we can potentially engineer features like "usable space" instead of having various features for area.