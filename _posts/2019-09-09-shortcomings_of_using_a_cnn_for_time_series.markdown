---
layout: post
title:      "Shortcomings of Using a CNN for Time Series"
date:       2019-09-09 20:00:38 +0000
permalink:  shortcomings_of_using_a_cnn_for_time_series
---


In a previous post I detailed how I used Convolutional Neural Networks on stock chart images to predict future stock price movement.  I would not recommend anyone risk real money using the process that I posted to my Github page but it was successful as a proof of concept.  I was able to get statistically significant results in predicting both the direction and magnitude of the stock’s subsequent movement but frankly it left a lot to be desired.  The process was very expensive and time consuming and there wasn’t much that I could do at the end of it to determine how useful a prediction was.  I went in search of a different method for analyzing time series data and found a technique called Dynamic Time Warping (DTW).  DTW is not new or particularly sophisticated but it is different enough than what I did before that it is my next step in the process of accurately predicting stock movements.  I think that it is most easily explained as the more sophisticated cousin of correlation that allows for “flexibility” in evaluating the similarity of a curve. 

![](https://www.google.com/url?sa=i&source=images&cd=&ved=&url=https%3A%2F%2Fwww.pinterest.com%2Fpin%2F505669864405381122%2F&psig=AOvVaw3wxgs15N13QIrdbrLVJEtj&ust=1568144881002763)

For example, a sin and cos curve are identical curves that are shifted; but a correlation study would find them to be very different.  DTW on the other hand, has the ability to account for a shift and would see the sin and cos curves as very similar.  This is likely a big advantage in scoring the similarity of time series with large amounts of noise, like a stock price curve.  The idea going forward would be to compare the curve in question to as many historical curves as possible to find the most similar one and use it to make a prediction based on the movement following the historical curve.  One huge advantage of this method is the savings on the time to create the stock chart images, the memory to save all of them and the computational expense in comparing them.  This allows me to run orders of magnitude more charts through the system in the same time as the CNN would allow.

Overall the CNN was a good starting point for predicting stock movement and showed promise, but ultimately it is not the best tool for the job and dynamic time warping looks like a better solution.
