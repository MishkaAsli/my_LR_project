Abstract: The goal of this project was to use webscraping and different types of regression modeling to predict the gross pay for domestic box office movies. I worked with data from boxofficemojo.com and leveraged both numerical and categorical features including budget, running time, and distributors to predict the target. This analysis will be useful to potential film investors and aid them in investing in movies with the potential for the highest domestic gross pay. 

Design: 
The data was provided by boxofficemojo.com. Predicting the domestic gross pay for potential film investors will allow them to provide investments with a higher potential rate of return. 

Data:
The dataset contains 1200 movie pages and 30 features (including dummy variables) of which 4 were deeply analyzed and will be presented on. A few feature highlights include budget, 20th Century Fox, Sony Pictures, Action Genre. Features were either analyzed normally if they were already numerical or through dummy variables if they were originally a categorial feature. About 2/3 of the features were created through dummy variables. 

Tools:
•	Beautiful Soup, Regular Expression for webscraping
•	Scikit-learn, numpy, pandas for EDA, feature engineering and modeling
•	Matplotlib and Seaborn for plotting

Algorithm:
Webscraping:
•	Started by webscraping with Beautiful Soup the last 5 pages of the Top Lifetime Gross Pay for movies with MPAA rating of PG lists. 
•	The features originally webscraped are: title, MPAA rating, Gross Domestic Pay, Gross Worldwide Pay, Budget, Lifetime Ranking, Running Time, Distributor, Genre, Top Director, Top Actor. 
•	Added all the data extracted to a dictionary and then converted it to a Data Frame. Split the top 3 Genres into separate columns to convert them to dummy variables later on. 

Exploratory Data Analysis:
•	Removed any duplicate titles. Then I filled any Worldwide Gross Pay NAs with their respective Domestic Gross Pay.
•	Throughout my analysis, I was performing other forms of EDA like checking .info(), .describe(), and .value_counts() among others.

Feature Engineering:
•	Created an ‘Other’ category for Distributor, Top Actor, First Genre, Second Genre, Third Genre, to group any categories with lower counts together. 
•	Log transformed Domestic Gross Pay and Budget to scale the values.
•	Made dummy variables for Distributor and First Genre. 
•	After splitting the data, filled any Running Time, and Budget NAs in the training and test sets with the median of the training set. 
•	Squared the budget feature to linearize it. 

Modeling:
•	Split the data into train and test.
•	Narrowed the features down to: ['budget', 'running_time', 'log_budget', 'distributor_Metro-Goldwyn-Mayer (MGM)', 'distributor_Other_Dist', 'distributor_Paramount Pictures', 'distributor_Sony Pictures Classics', 'distributor_TriStar Pictures', 'distributor_Twentieth Century Fox', 'distributor_Universal Pictures', 'distributor_Walt Disney Studios Motion Pictures', 'distributor_Warner Bros.', 'budget2']
•	The target is: Domestic Gross Pay.
•	The features that are most correlated to Domestic Gross Pay are: Budget, Running Time, 20th Century Fox Distributor, Walt Disney Studios Motion Pictures Distributor, and Warner Brothers Distributor. 
•	Then I standardized the data to perform LASSO modeling.
•	Found the optimal alpha and cross validated through the LASSO model.
•	Narrowed down the features to the features with the highest coefficients in the LASSO model and most of the coefficients were close to 0. 

Findings:
•	Test Linear Regression Model R2: 0.15
•	Test Lasso Regression Model R2: 0.1798

Communication:
This portion will be completed through the 5-minute presentation. 
