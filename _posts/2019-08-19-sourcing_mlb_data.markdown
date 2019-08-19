---
layout: post
title:      "Sourcing MLB Data"
date:       2019-08-19 16:15:13 +0000
permalink:  sourcing_mlb_data
---


For the Module 3 final project our assignment was to create a classification model from a data set of our choice. Being a trader, I have always been in the business of trying to predict “random” events and I wanted to test my skills at a new type of prediction: Major League Baseball games. To be honest I though that gathering the data would be the easiest part, given that baseball is such a quantifiable sport and there is so much data publicly available. I was very wrong. I admit that the data set that I envisioned wasn’t exactly like the ones readily available on ESPN.com but all of the data I was looking for was very normal baseball statistics.

What I was hoping to gather was basically a snapshot of the home and away team as seen just before the start of each game. I wanted to know each team’s full season record and their winning percentage in the last 10 games (basically how hot or cold are they). I also wanted the statistics for each starting pitcher, bullpen and offensive line-up over the last 10 days in order to give a full picture of how each team is playing recently. This proved to be a very tedious and time consuming task because for every game in the season, I had to make a separate call to multiple databases. On top of that, different databases had different team abreviations, meaning that I had to make functions match one database to another. A particular database had lots of great data with the large exception that any data beyond the 9th inning was not included, requiring a tedious work around. I also ran into the problem of multiple pitchers having the same name pitching against each other! Double-headers threw things off and required me to jump through another hurdle. All in all, I learned first hand that when people say 80% of the data science process is gathering and preparing data; they are very correct. In this case I believe that it was worth it because I have a unique data set that resulted in my model being able to beat the Vegas odds with statistical significance.
