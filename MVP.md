Goal of the project: My goal is to predict the domestic gross pay for future movie releases for investors and see which features affect the gross pay the most.
What I’ve done so far:

Removed some duplicate titles
if worldwide gross pay was null, i made worldwide gross pay equal to domestic gross pay.
mapped the few least represented genre, actors, and distributors to an ‘other’ category
then i split my data into train and test with test being 20% of the data
if running time or budget had any null values in the train or validation date, I updated it to the median value of the train data.
After this my R^2 is currently 0.8813 and I looked at any initial correlations. worldwide gross pay and domestic gross pay are very correlated. budget and running time to domestic gross pay are slightly correlated


What I will be doing next:
Save dataframe to a CSV
Continuously check R2 and MAE
Create dummy variables for genre, distributor and top actor
Create OLS model on train data
Cross validate on train data (80% of total dataframe) via ridge regression and LASSO regression since my test data R2 is slightly less than my train data R2


<img width="753" alt="Screen Shot 2021-09-28 at 5 09 28 PM" src="https://user-images.githubusercontent.com/77215072/135182172-cb2821a1-a5a8-4252-8e37-79873a1b946a.png">


