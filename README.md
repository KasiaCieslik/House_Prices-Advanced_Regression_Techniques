# House_Prices-Advanced_Regression_Techniques
>>Note: This is **work-in-progress**. Project which I do during a Frauenloop Machine Learning Bootcamp in winter 2021.

Repository for source code of kaggle competition: 
[House Prices - Advanced Regression Techniques](https://www.kaggle.com/c/house-prices-advanced-regression-techniques)
### Overview
The main goal of the project is to predict the **Sale Price** using regression techniques. 

From Kaggle:
*Ask a home buyer to describe their dream house, and they probably won't begin with the height of the basement ceiling or the proximity to an east-west railroad. But this playground competition's dataset proves that much more influences price negotiations than the number of bedrooms or a white-picket fence. With 79 explanatory variables describing (almost) every aspect of residential homes in Ames, Iowa, this competition challenges you to predict the final price of each home.*


### Data preprocessing
I performed basic data processing like:
- unskewing some columns
- removing unimportant columns
- encoding categorical features

### Feature engineering
I added multiple features based on the original columns. Two worth mentioning (with high feature importance) are:
NEW_TOTALQUAL_index - A cross feature that combines OverallQual * GarageArea * GrLivArea
NEW_Total_sqr_footage - Sums up total area of house.


### Competition metric
The official metric used (on kaggle and this repo) is the RMSE between the lograithms of the real price and predicted price.


|    | model                       |    score | feature_engineering   | leaderboard_score   |
|---:|:----------------------------|---------:|:----------------------|:--------------------|
|  0 | RandomForestRegressor       | 0.142496 | no                    |                     |
|  1 | LinearRegression            | 0.153985 | yes                   |                     |
|  2 | RandomForestRegressor       | 0.142053 | yes                   |                     |
|  3 | XGBRegressor                | 0.142106 | yes                   |                     |
|  4 | ElasticNet                  | 0.130227 | yes                   |                     |
|  5 | VotingRegressor             | 0.12466  | yes                   |                     |
|  6 | VotingRegressorGridsearched | 0.122292 | yes                   |                     |


Cross validation scores are aligned with leaderboard scores, this means that a regular KFold validation strategy is good for this problem/competition.


### Setup
- install requirements.txt
- run jupyter-notebook.

Data for this competition can be found in the data directory.


### Next steps
- Improve data cleaning (removing outliers)
- Model with important features only
