# Predicting Dow Jones Industrial Average (DJIA) stock performance direction (up or down) based on Top 25 Headlines

Please use the below link to see the project file (ipynb) in NBviewer for better view
https://nbviewer.jupyter.org/github/nitish20899/Predicting-DJIA-stocks-direction-based-on-Top-news-headlines/blob/main/predicting-stocks-up-or-down-87-accuracy.ipynb


## Table of Contents
* [Introduction](#Introduction)
* [Aim of the project](#Aim)
* [About the Dataset](#Dataset)
* [Process](#Process)
* [Findings](#Findings)
* [Legality](#Legality)



## Introduction

The Dow Jones Industrial Average, Dow Jones, or simply the Dow, is a stock market index that measures the stock performance of 30 large companies listed on stock exchanges in the United States.
The 30 stocks which make up the Dow Jones Industrial Average are: 3M, American Express, Amgen, Apple, Boeing, Caterpillar, Chevron, Cisco Systems, Coca-Cola, Disney, Dow, Goldman Sachs, Home Depot, Honeywell, IBM, Intel, Johnson & Johnson, JP Morgan Chase, McDonald’s, Merck, Microsoft, Nike, Procter & Gamble, Salesforce, Travelers, UnitedHealth, Visa, Walgreens, and Walmart

As we know there is great relationship between stocks and daily news. So I had selected a Dataset from kaggle (Daily News for Stock Market Prediction).



## Aim 

This project is all about predicting whether the (DJIA) stock market performance (Dow 30) goes up/maintain or down based on Top 25 news headlines taken from Reddit website (Daily News for Stock Market Prediction)(https://www.reddit.com/r/worldnews/?hl=)

The dataset is taken from Kaggle (https://www.kaggle.com/aaron7sun/stocknews)



## Dataset

The Dataset is present in the file named CombinedNewsDJIA.csv
The first column is "Date", the second is "Label", and the following ones are news headlines ranging from "Top1" to "Top25"
The Label value is "1" when DJIA Adj Close value rose or stayed as the same and "0" when DJIA Adj Close value decreased

for task evaluation,I considered from 2008-08-08 to 2014-12-31 as Training Set, and Test Set is then the following two years data (from 2015-01-02 to 2016-07-01). This is roughly a 80%/20% split.



## Process

1) Filling null values in the dataset with median
2) Combining all the headlines into one news
3) Cleaning the text by removing punctuations and changing all the letters to lowercase
4) Applying countvectorizer to all the headlines
5) Using different ML Algorithms (Random forest , XGBoost , Catboost) to predict the stocks direction
5) Visualizing the results and choosing the best algorithm based on requirements



## Findings

The most repeated words in the Dataset (trainset and testset) is shown below

for train set
<p align="center">
  <img width="460" height="300" src="https://user-images.githubusercontent.com/63724986/98461972-afbc4000-21d6-11eb-9fd2-1007ebe06fcf.JPG">
</p>

for test set
<p align="center">
  <img width="460" height="300" src="https://user-images.githubusercontent.com/63724986/98461997-d8dcd080-21d6-11eb-8ba7-dab9fef9d469.JPG">
</p>

scores of the different models are shown below (note: hp=hyperparameter tuning )
**Highest accuracy achieved among all these models is 87%**
<p align="center">
  <img width="460" height="300" src="https://user-images.githubusercontent.com/63724986/98462319-9f599480-21d9-11eb-8e5f-855521d3301f.gif">
</p>

True positive and False negative values plays a major role in selecting the model you want, for example if you want a model that predicts more True positive values and you dont care about False negative values then you can choose the model which predicts more True positive values.If you care more about False negative values then your choice of model will be different.you can see the below graph which show TF and FN values for each model
<p align="center">
  <img width="460" height="300" src="https://user-images.githubusercontent.com/63724986/98463956-63c4c780-21e5-11eb-9925-dd414f4daec7.gif">
</p>

Based on your requirements you can choose which models is the most needed one for you



## Legality

This is a personal project made for non-commercial uses ONLY. This project will not be used to generate any promotional or monetary value for me, the creator, or the user.

Dont invest on stocks based on the predictions made using these models, Investing on stocks required more knowledge other than data science.If you wish to, then do at your own risk.
