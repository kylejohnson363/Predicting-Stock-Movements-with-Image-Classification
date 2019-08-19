# Predicting-Stock-Movements-with-Image-Classification
Use Convolutional Neural Networks on stock chart images to predict a stock’s 10 day return

Kyle Johnson

For this project we were tasked with creating a neural network to solve a classification problem. The problem that I have chosen is predicting a stock's movement 10 days into the future by using convolutional neural networks on stock chart images. I approach this as both a multiclass problem and a binary problem. Please follow along with the notebooks that detail this process.

### Notebook 1 - Data Gathering
Please see the notebook titled "Data_Gathering". In this notebook I use a Yahoo Finance API to source historical daily price data going back to 2010 on the 30 stocks in the Dow Jones Industrial Average and then create stock chart images and other attributes to be used in modeling.

### Notebook 2 - CNN Multi-Categorical Classification
Please see the notebook titled "CNN_Multi_Classification". In this notebook I create multi-categorical classification model that attempts to predict the direction and magnitude of a stock's movement. For this model I define success as creating predictions whose standard deviation of error is less than the standard deviation of returns for all trades.

### Notebook 3 - CNN Binary Classification
Please see the notebook titled "CNN_Binary_Classification". In this notebook I create a binary classification model that attempts to predict if a stock will be higher or lower 10 days into the future. For this model I define success as creating predictions that lead to trading profits that exceed the benchmark of the Dow Jones Industrial Average itself.

# Summary of Findings:
-In the CNN multi-categorial classification model we achieved our goal of making a model with a smaller standard deviation of error than all stock's standard deviation of returns. This may seem useless on its surface but a model that can consistently do this would be of enourmous benefit to options traders due to the ability to take limited risk positions that have large payouts if the underlying stock lands in a specific zone.

-In the CNN binary classification model we achieved our goal of making predictions that outperform the Dow Jones Industrial Average. The model outperformed in bullish and bearish markets and if these results can be repeated in live trading, would be of great benefit to traders, investors and money managers.

# Further Study:
While these models did provide compelling results, it would take a fool to put real money at risk using these techniques alone and I advise against it in the strongest possible way.

Areas of further study:

-The architecture of the neural network in order to optimizethe model for reading stock chart images.

-The size (days included in each chart), detail (number of pixels), data (include volume and other data) and indicators contained within the input images.

-The number of stocks to include. Further study should include stocks that are no longer in the Dow Jones or even no longer publically traded in order to avoid survivorship bias.
