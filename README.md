# Predicting-Stock-Movements-with-Image-Classification
Use Convolutional Neural Networks on stock chart images to predict a stock’s 10 day return

Kyle Johnson

Blog post:  https://kylejohnson363.github.io/forecasting_stock_movements_with_image_classification

### Project Motivation
The use of stock charts to inform trading and investing decisions has been prominent since long before computers when traders would draw their charts by hand in search of exploitable patterns and insights.  This project builds on that by applying image recognition techniques, specifically Convolutional Neural Networks, on candlestick stock chart images in search of actionable insight.

##### Please see the notebook titled "Summary_Start_Here" for a detailed road map through this project in order fully understand the process.

### Process Overview

The data for this project was daily stock price data on all 30 stocks in the Dow Jones Industrial Average sourced from the Yahoo Finance API and then made into stock chart images.  Each image is of the preceeding 100 trading days and the value being predicted is the stock price 10 days into the future.  Each image was a 107 pixel square, meaning that it is quite grainy and does not convey a lot of information.  The blue line is a 20 moving average.  Once the images are created, they are split into training, validation and test sets as described below and then fed into the neural network which output a prediction.  The split was done in this manner so that we are always using the past to predict the future.

![Diagram](https://github.com/kylejohnson363/Predicting-Stock-Movements-with-Image-Classification/blob/master/Diagram.JPG)

### Binary Results
This approach used a binary classification CNN to predict if a stock would move up or down.  The results of the model are compared against the Dow Jones Industrial Average over the same out-of-sample time frame and shows that our portfolio almost doubles the return of our benchmark (56% vs 31%).  Not only does our portfolio outperform the market, it out performs both when the market goes up and when it goes down meaning that the network is adding value by identifying useful predicitve features within a chart.

![Binary](https://github.com/kylejohnson363/Predicting-Stock-Movements-with-Image-Classification/blob/master/Binary%20Results.JPG)

### Multi-Categorical Results
This approach used a multicategorical CNN to predict both the direction and the magnitude of a stock's movement.  The goal is for the predictions to have a smaller standard deviation of error than the corresponding standard deviation of returns.  This may seem abstract but it is extremely valuable to options traders who can place complex bets about when a stock will be in a certain price range.  These very specified bets can have very large payoffs when they are correct.  The negative value of the bartlett coefficient means that our standard deviation of error is smaller than our benchmark and the p-value indicates that it is statistically significant, meaning that we have achieved our goal.

![Multi](https://github.com/kylejohnson363/Predicting-Stock-Movements-with-Image-Classification/blob/master/Multi%20Results.JPG)

# Summary of Findings:
-In the CNN binary classification model we achieved our goal of making predictions that outperform the Dow Jones Industrial Average. The model outperformed in bullish and bearish markets and if these results can be repeated in live trading, would be of great benefit to traders, investors and money managers.

-In the CNN multi-categorial classification model we achieved our goal of making a model with a smaller standard deviation of error than all stock's standard deviation of returns. This may seem useless on its surface but a model that can consistently do this would be of enourmous benefit to options traders due to the ability to take limited risk positions that have large payouts if the underlying stock lands in a specific zone.

# Further Study:
While these models did provide compelling results, it would be foolish to put real money at risk using these techniques alone and I advise against it in the strongest possible way.

Areas of further study:

-Adjust the architecture of the neural network in order to optimize the model for reading stock chart images.

-Try many values for the size (days included in each chart), detail (number of pixels), data (include volume and other data) and indicators contained within the input images.

-The number of stocks to include. Further study should include stocks that are no longer in the Dow Jones or even no longer publically traded in order to avoid survivorship bias.

-Create a "blended" Neural Network that incorporates both numerical and image data.
