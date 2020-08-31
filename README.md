# Real Estate Price Predictor
The goal of this project was to predict real estate sales prices for houses located in Ames, Iowa between 2006-2010. I did visualization, feature engineering, and explored both linear and tree based regression models.

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

![Images](/Neigh_Sale_Price_FINAL.png)

By looking at a correlation matrix, we are able to see that OverallQual (Overall Quality of the home's finishes), GrLivingArea (Living area above grade), and ExterCond (External Condition) are the non categorical variables most correlated with the Sale Price. In addition, we can see some collinearity between features. TotRmsAbvGrd (Total rooms above grade ) and GrLivingArea (Living area above grade) are highly correlated, which makes sense because as the number of rooms increase, the square footage increases and vice versa. GarageCars and GarageArea are also highly correlated for the same reason.

![Images](/heatmap.png)
