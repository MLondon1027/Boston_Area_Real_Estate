What problem am I trying to solve?

Proposal 1) I am trying to solve the problem of predicting sale prices for real estate in the Boston metro area.
Proposal 2) I am trying to predict which properties will sell in the next 12 months. This will be useful for real estate agents to know 
who to direct their marketing efforts towards.

Where I am obtaining my data?

As a licensed real estate agent in Massachusetts, I am able to pull data from the Massachusetts MLS. Data includes last sale date, last sale price, year built, 
levels, bedrooms, bathrooms, lot size, style, basement, condition, etc.

I can pull the data from the 231 zip codes listed on bestplaces.net as zip codes that are part of the Boston-Cambridge-Newton Metropolitan Statistical Area. 
I will look at data from the past 5-10 years.

I can also just look at one community. I would choose Needham, MA because this is where I used to sell and build property. I can look at which properties sold in the past 5 years. I can then cross reference those addresses with data from the following website:
http://epas.csc-ma.us/PublicAccess/Pages/ParcelSummary.aspx?MenuID=3&LinkID=467901&Commcode=199
http://epas.csc-ma.us/PublicAccess/Pages/Residence.aspx?MenuID=2

If I can scrape this data, I will be able to have more information on the particular property (# bedrooms, # bathrooms, etc).

I would also like to add the school district as a variable for each property. The elementary school district determines which part of town the property is in.
http://www.needham.k12.ma.us/UserFiles/Servers/Server_64429/File/Departments/School%20Committee/StreetList_SchoolDist_2019%20(1).pdf


Models and Feature Engineering

Proposal 1)
I am planning on using time series, linear regression and other regression based models to determine predicted sale price.
Proposal 2)
I am planning on using random forest, knn, and other classifiers to determine if the home is likely to sell in the next 12 months

Feature engineering could include adding sale price/square foot 
