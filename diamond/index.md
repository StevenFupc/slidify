---
title       : How much is the diamond?
subtitle    : Predict the price for a given weight with linear Regression Model
author      : Steven Fu
job         : Software Developer
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction (Slide 2)

How much is the diamond?

This Shiny App is to display the relationship of weight and price of diamond, and to provide prediction of price for a given weight using linear regession.

For a copy of the Shiny App:

-URL: https://stevenfupc.shinyapps.io/devdataprod-011/

-GitHub: https://github.com/StevenFupc/devdataprod-011

---
## Take a look at the dataset (Slide 3)

The diamond dataset is from the build-in dataset.
To get the data use library(UsingR); data(diamond).

Take a look the dataset:

```r
    library(UsingR)
    data(diamond)
    str(diamond)
```

```
## 'data.frame':	48 obs. of  2 variables:
##  $ carat: num  0.17 0.16 0.17 0.18 0.25 0.16 0.15 0.19 0.21 0.15 ...
##  $ price: int  355 328 350 325 642 342 322 485 483 323 ...
```

--- 
## Regression Model (Slide 4)
The relationship of price and weight is shown below(linear regression).

![plot of chunk plot](assets/fig/plot-1.png) 

--- 
## Prediction (Slide 5)
User enters a weight in carats (0.15 - 0.35).
The app will predict the price and the range using linear regression model.
For example, user enters 0.20 as weight.

```r
library(UsingR)
data(diamond)
fit <- lm(price ~ carat, data = diamond)
values<-predict(fit, newdata = data.frame(carat = 0.20 ), interval = "prediction")
values
```

```
##        fit      lwr      upr
## 1 484.5791 419.8196 549.3385
```
The 484.5790631 is the predicted price; 
and 419.8196032 ~ 549.3385231 is the predicted range.

