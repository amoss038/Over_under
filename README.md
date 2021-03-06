# Over_under: Investing In Sport Outcomes ? 

![Alt text](images/download.jpg?raw=true "NBA")


----------------------------------------------------------------------------------------------------------------------------------

## Abstract

Sports gambling, when done responsibly can be a great way to increase the entertainment values of sporting events. And, in some cases a way to generate income. This projects aims to bridge the gap between Data Science, predictive analytics, and sports wagering for the common fan. Sports gambling is a very difficult task to do consistently well and hopefully this project will provide some insight as to why that is so as well as give any sports fan the tools and strategies to lose less money or perhaps even make some.

----------------------------------------------------------------------------------------------------------------------------------


## Background and Motivation

As a blogger of sports gambling content I understand the balance between analytics and art form when it comes to predicting sports outcomes. Data has a lot to do with it, but the numbers do not paint the whole picture. We can design predictive models that have the capability to predict outcomes fairly well, but machine learning models are missing the human component. For example, how to we quantify player sentiment, or how tired they are because those factors surely have an effect on the outcome of the game. This projects ignores that for now and focuses strictly on the data. 


----------------------------------------------------------------------------------------------------------------------------------

## The Kappa Theory

Theoretically, whenever Vegas or an Oddsmaker set a bet line it should be considered the mean of a normal distribution. That is why sports gambling is so difficult because there is literally a 50/50 chance the outcome ends up on either side of that bet line. And, this doesnt even take into consideration how odds effect a gambler's chances. Therefor, in this project I explore a theory via a metric I designed called Kappa. Kappa is meant to create thresholds around a bet line to identify specific betting positions that may have more value for specific games.

![Alt text](images/dist.jpg?raw=true "NBA")

----------------------------------------------------------------------------------------------------------------------------------


## Research Question & Data


Question: Will creating thresholds using Kappa to identify valuable betting positions increase our chances of winning a bet?

The question is simple enough, but the answer is more complex as we begin to explore the Data and model. 

The Data is scraped fro NBA.com utilizing the last 7 years of games logs for every NBA regular season game. I combined this data with historical betting data aggregated from Sportbookreviewsonline.com. Predicting the score of a sporting event is difficult enough, but made even more complex of an issue because none of the information for the game we are trying to predict is available. Therefor, we need some way of fabricating data with predictive power to predict the outcome of that game before it is played. This model use

I compared 3,5,7, and 10 game rolling averages for the features and predictors that the model will be trained on. And, it turns out that a 7 games rolling average has the best predictive power in terms of minimizing the error metric MAE.


----------------------------------------------------------------------------------------------------------------------------------

## Results 

### Initial Results 

Random Forest Using 7 Game rolling Average.

- Winning Percentage:  52.0% 
- MAE: 13.0
- Overall return: $-3,095

Below is a visual of how my predictions compare to what the odds threshold is or betting line and the actual total of the game Over a snapshot of 20 games that my model analyzed. As you can see my model is able to capture much of the trends in terms of the actual game total points and the betting threshold or betline.

![Alt text](images/predictions.jpg?raw=true "NBA")


** Since the model is able to capture the trends relatively accurately maybe there is a way to increase our chances of winning by introducing Kappa?

## Kappa 

![Alt text](images/kappa.jpg?raw=true "NBA")


** Note That this is only using the testing set that is apart of the training data. The model currently seems to be a little overfit because when I tried validating the model with the holdout data Kappa 3 caps out at 51.0% accuracy with a MAE of 16. Unfortunaly, this result produces a negative return and it is recommended not to put this model into production until I increase the testing accuracy. However, these initial results are promising because it supports the validity of the Kappa metric provided we are able to keep the MAE to around 13. 

*** The next steps would be to introduce more data, new models, and feature engineering to lower the MAE of the holdout to approximately 13, which signifies a profitable model utilizing the Kappa metric.






