# Crypto-Prediction-Model
Machine learning model based on BigData. Created using hadoop an spark

The exploratory analysis was made possible using the <a href="https://github.com/smridh99/Crypto-Prediction-Model/blob/main/btc.csv">dataset from Kaggle</a>


 A user will input their portfolio (all coins they currently have) and we will tell give them a recommendation on what they should do. For example, if they are holding BTC and ETH and our model says that in 24 hours, BTC will rise x% and ETH will rise y%, then you should ...

How To Do This: At a high level, linear regression. Two ways we can do this:

    Run a seperate linear regression for each coin
    Use a single linear regression model. We would then need indicator variables for each coin in the model.

With either method, we still need to do feature selection. This would be what we input to our linear regression. Since aggregating by day wouldn't give us "big data" anymore, we will leave the data in minute format. With this, possible features to try are:

    Total monetary value traded in a minute (amount in the dataframe - no work needed)
    Opening price for that minute (open in the dataframe - no work needed)
    High price for that minute (high in the dataframe - no work needed)
    Low price for that minute (low in the dataframe - no work needed)
    Close price for that minute (close in the dataframe - no work needed)
    Number of transactions for that minute (count in the dataframe - no work needed)
    Volume of the token for that minute (vol in the dataframe - no work needed)
    Length of the previous increasing run (would require SQL work to obtain)
    Average rate of change of previous 15 minutes - an estimate of the derivative (would also require SQL work to obtain)
    Max - Min for previous day
    Time of day indicator (maybe morning, afternoon, evening)
    If we decide to go with one single regression (then we'd need multiple coin indicators)

Next, would be training our model. We could use SparkML or do it ourselves or both. I personally think it would be cool to do both and then compare. Doing it ourselves would entail performing stochastic gradient descent to find the optimal weights.


Follow here for the detailed walkthrough: <a href="https://github.com/smridh99/Crypto-Prediction-Model/blob/main/Walkthrough%20prediction%20model.ipynb"></a>

