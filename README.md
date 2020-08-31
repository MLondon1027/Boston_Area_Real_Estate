# Real Estate Price Predictor
The goal of this project was to predict real estate sales prices for houses located in Ames, Iowa between 2006-2010. I visualized the data, did feature engineering, and explored both linear and tree based regression models.

# Background
I have a background in several areas of the real estate sector, including developing, listing, and selling homes. The sale price of a home is difficult to predict and relies on much more than the typical features one would think of, such as size and location. These still remain important. However, there are other factors such as macroeconomic indicators and competing inventory factors that make it notoriously difficult to model home prices. In addition, real estate is valued at the micro level; each community places a different weight on each factor.

# Goals
The two main goals for this project were to build a model that closely predicts sales price for homes in Ames, Iowa based on the given factors and to determine which features are most impactful towards sale prices.

# Data
The data was in downloaded from a Kaggle dataset and in csv form. There was a lot of data cleaning that needed to be done prior to modeling. I was able to use domain knowledge in several cases. For instance, I filled missing values for LotFrontage with the median LotFrontage for that home's particular neighborhood. 

The data set began with 2,919 properties and 79 predictor variables. After sifting out variables with limited importance or datapoints and properties with no sale value, we were left with 1,460 properties and 71 predictor variables.

# Exploration
I analyzed the distribution of the sale price and we can see that the majority hover in the $100,000-$200,000 range, with a mean sale price of $180,921 and median sale price of $163,000. 

![Images](/images/Dist_Sale_Price.png)

The properties were sold between 2006-2010. Upon an analysis of the count of homes sold each year, we can see that the number drops in 2010. This is likely due to the recession.

![Images](/images/Year_Sold.png)

Location is often assumed to be the most important variable in the price of real estate. By looking at the distribution of the sales price for various neighborhoods, we can see that the three highest priced neighborhoods are Northridge, Northridge Heights, and Stonebrook.

![Images](/images/Neigh_Sale_Price_FINAL.png)

By looking at a correlation matrix, we are able to see that OverallQual (Overall Quality of the home's finishes), GrLivingArea (Living area above grade), and ExterCond (External Condition) are the non categorical variables most correlated with the Sale Price. In addition, we can see some collinearity between features. TotRmsAbvGrd (Total rooms above grade ) and GrLivingArea (Living area above grade) are highly correlated, which makes sense because as the number of rooms increase, the square footage increases and vice versa. GarageCars and GarageArea are also highly correlated for the same reason.

![Images](/images/heatmap.png)

# Modeling

I created a baseline model with features that appeared important to the sale price during the EDA process. The baseline model used the following features:
1) Neighborhood
2) Living Area Above Grade
3) Overall quality
4) Lot size
5) Year remodeled
6) Building type
7) Total basement square feet

I used both Linear Regression and Gradient Boosted Regressor models. The Gradient Boosted Regressor model outperformed the Linear Regression model, performing with an RMSE of $26,056 and a MAE of $17,612. After looking at the residual plots, I determined that the models were struggling to predict on the highest priced homes, particularly over $600,000. After some deeper digging, I determined that the model was failing on homes that were larger than 4,000 square feet and removed those four properties.

I did some feature engineering (such as combining the number of full and half baths to total bathrooms and creating an Interior Age variable that was the most recent year of year built and year remodeled). I determined that including all of the features helped the model perform best. I used GridSearch to hypertune the model parameters.

The final model resulted in an RMSE of $19,343 and an MAE of $13,283. 
