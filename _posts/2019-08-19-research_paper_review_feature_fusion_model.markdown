---
layout: post
title:      "Research Paper Review: Feature Fusion Model"
date:       2019-08-19 17:52:48 +0000
permalink:  research_paper_review_feature_fusion_model
---


In February of 2019, Taewook Kim and Ha Young Kim published a paper titled "Forecasting stock prices with a feature fusion LSTM-CNN model using different representations of the same data".  The basic goal of the paper was to use a combined model that outperformed each individual model as well as the benchmark of the S&P 500 index.  The data used for this paper was the open, high, low and close prices on minute-by-minute SPY (SPDR S&P 500 ETF) ticker data from October 14, 2016 to October 16, 2017. The data was split into training, validation and testing sets in the following way in order to avoid using the future to predict the future.
![](https://journals.plos.org/plosone/article/figure/image?size=large&id=info:doi/10.1371/journal.pone.0212320.g001)
For each individual prediction, the previous 30 minutes of data is used to make a prediction 5 minutes into the future as shown below.
![](https://journals.plos.org/plosone/article/figure/image?size=large&id=info:doi/10.1371/journal.pone.0212320.g002)
The first of the two models that was tested before fusion was a Convolutional Neural Network on four types of stock charts to determine the best image type.
![](https://journals.plos.org/plosone/article/figure/image?size=large&id=info:doi/10.1371/journal.pone.0212320.g003)
The combination of (a) and (d) was found to be the best image to use and resulted in input images that looked like (a) shown below.
![](https://journals.plos.org/plosone/article/figure/image?size=large&id=info:doi/10.1371/journal.pone.0212320.g004)
The second model used was the LSTM for time series data and used price and volume data as inputs to create a predicted price output as shown below.
![](https://journals.plos.org/plosone/article/figure/image?size=large&id=info:doi/10.1371/journal.pone.0212320.g005)

The combined fusion model used an architecture as shown below to take insights gained from the image recognition and LSTM models to make a single prediction.
![](https://journals.plos.org/plosone/article/figure/image?size=large&id=info:doi/10.1371/journal.pone.0212320.g011)
There were several metrics used for evaluating the performance of the different models but the only one that really matters in this case is the resulting profit.  In the image below we see that the benchmark of buy and hold generated a return of 3%, the best CNN returned 15.9% and the LSTM returned 16.3%; which are both significant improvements over the benchmark.  However, we find that the feature fusion model is the best performing model with a return of 17.4%.  This study is a successful proof of concept that both image recognition and time series techniques have the potential to add value to a trading plan and that a fusion of these methods can improve the results even further.
