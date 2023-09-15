# Predicting Goals in an NHL Game

## Project/Goals
Can we predict the total amount of goals scored in an NHL game? This is a model using the NHL API with various regression techniques.
Predicting goals can be important due to how impactful it is on a game, but also indirect through sports betting outlets.

## Process
##### 1. NHL API
Using the NHL API, season linescore and boxscore data were acquired from 2017/18-2022/23.
After establishing the dataframe, a csv was exported to reduce amount of code required.

##### 2. Joining Data
Using the previously exported csv files, I merged the dataframes together with a full outer join in order to set up to clean.
Cleaning the data included removing all NaN values, any duplicates (based on shop name and coordinates) and then using the cleaned data to run regression models.

##### 3. Feature Engineering
Using the linescore and boxscore (which are not considered advanced statistics), I created total shot opportunities and shots per goal and fed that into the model.

##### 4. Building Model
Various regression techniques were use to see which fit the model better - linear regression, random forests, gradient boosting, k-nearest neighbours, xgboost and Poisson.
Poisson regression seemed to have the best balance for predictive capability and not overfitting the training data.

##### 5. Training/Testing
I used all the data from 2017/18-2021/22, including the first 100 games of the 2022/23 season, to predict the subsequent games.

## Results
The results were the following:

2022-10-25, Montreal Canadiens (H) vs Minnesota Wild (A)

Predicted: 6.336908 | Actual: 4

2022-10-25, Detroit Red Wings (H) vs New Jersey Devils (A)

Predicted: 6.310530 | Actual: 8

2022-10-25, Chicago Blackhawks (H) vs Florida Panthers (A)

Predicted: 6.19779 | Actual: 6

## Challenges 
The main challenges included setting up the API and then choosing which model would be the best for the data.
While the model did fairly well on numerical data, it does not do a good job of evaluating player talent and does not know how to empirically weigh that talent on any given night.

## Future Goals
With more time, the model could include "expected goals per team", which can be considered just one step further from total goals. Furthermore, I'd like to implement some sports betting odds in order to capture the essence of wagering on sports.
