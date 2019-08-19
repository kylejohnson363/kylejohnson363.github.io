---
layout: post
title:      "Research Paper Review: CNN failings and the CoordConv Solution"
date:       2019-08-19 19:23:28 +0000
permalink:  research_paper_review_cnn_failings_and_the_coordconv_solution
---

In December 2018 a group of data scientists from Uber AI Labs published a paper called "An intriguing failing of convolutional neural networks and the CoordConv solution".  In this paper they identify a set of seemingly simple tasks that include plotting a pixel in space given its coordinates and the reverse of that, identifying coordinates based on an input image.  
![](https://1fykyq3mdn5r21tpna3wkdyi-wpengine.netdna-ssl.com/wp-content/uploads/2018/07/image3-2-768x260.png)
It is surprising but standard CNNs performed very poorly and took a long time to do so.  Models were trained on up to a million parameters for as long as 90 minutes but still the best model only acheived 83% accuracy.
![](https://1fykyq3mdn5r21tpna3wkdyi-wpengine.netdna-ssl.com/wp-content/uploads/2018/07/image4-2-768x303.png)
In order to dive deeper into this problem, the authors visualized the area around the target pixel.  We see that in the training set, the prediction is fairly confident as shown by the mostly black pixels with a distinct white one. The middle row shows a test example that is barely correct and has a number of pixels that have a similar grey color, indicting a low level of confidence in the prediction.  In the bottom row, we see a test example that was wrong, displayed by the red box not being around the whitest pixel.
![](https://1fykyq3mdn5r21tpna3wkdyi-wpengine.netdna-ssl.com/wp-content/uploads/2018/07/image15.png)
The solution proposed by the authors is a CoordConv layer which adds two channels, one for the i coordinates and one for the j coordinates.
![](https://1fykyq3mdn5r21tpna3wkdyi-wpengine.netdna-ssl.com/wp-content/uploads/2018/07/image8-768x321.jpg)
In the image below, we can see that adding this layer solves the problem very well and very quickly.  The model acheives perfect accuracy after less than 20 seconds of training compared to the original model which acheieved only 83% accuracy after over an hour.
![](https://1fykyq3mdn5r21tpna3wkdyi-wpengine.netdna-ssl.com/wp-content/uploads/2018/07/image7-768x393.png)
![](https://1fykyq3mdn5r21tpna3wkdyi-wpengine.netdna-ssl.com/wp-content/uploads/2018/07/image10-1-768x211.png)
Revisiting the pixel visualization from above we see that the improved model has full confidence in all of its predictions.
![](https://1fykyq3mdn5r21tpna3wkdyi-wpengine.netdna-ssl.com/wp-content/uploads/2018/07/image1-1-768x396.png)

This is a very simple example meant to be a proof of concept.  The authors then applied this technique to teaching a neural nework to play Atari games.  In 6 of the 9 Atari games, the CNN with a CoordConv layer worked better or faster than a standard CNN; in 2 games they were simialar and in one game it was slightly worse.
![](https://1fykyq3mdn5r21tpna3wkdyi-wpengine.netdna-ssl.com/wp-content/uploads/2018/07/image14-1-768x374.png)
The authors conclude that the simple fix of adding a CoordConv layer has the potential to boost the performance of a wide range of applications and propose further work into the benefits in detection, language, video prediction and spatial transformer networks.



