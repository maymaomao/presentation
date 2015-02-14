---
title       : Predict Profit Based on Population
subtitle    : Develop Data Product Project Presentaiton in Coursera
author      : maymaomao
job         : Student
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Introduction

I will implement linear regression with one variable to predict profits for a food truck.Suppose you are the CEO of a restaurant franchise and are considering different cities for opening a new outlet. The chain already has trucks in various cities and you have data for profits and populations from the cities.

You would like to use this data to help you select which city to expand to next.

--- .class #id 

## See Data

The file data1.txt contains the dataset for our linear regression. Let's see the original data first,there are two columns representing Population of City in 10,000s and Profit in $10,000s.


```r
rdata<-read.table("../data1.txt",sep=",",header = F)
names(rdata)<-c("population","profit")
head(rdata)
```

```
##   population  profit
## 1     6.1101 17.5920
## 2     5.5277  9.1302
## 3     8.5186 13.6620
## 4     7.0032 11.8540
## 5     5.8598  6.8233
## 6     8.3829 11.8860
```

--- .class #id 

## Plotting

Scatter plot to visualize the data.

![plot of chunk plotting](assets/fig/plotting-1.png) 

--- .class #id 

## Linear Regression

Get the intercept and slope of the "best" straight line.


```r
fit<-lm(profit~population,data=data)
intercept<-fit$coefficients[1]
slope<-fit$coefficients[2]
fit$coefficients
```

```
## (Intercept)  population 
##   -3.895781    1.193034
```

--- .class #id 

## Prediction

When the population is 11.03 , using the "best" line to predict its profit:


```r
predict_population=11.03
slope*predict_population+intercept
```

```
## population 
##    9.26338
```
You can see the shinyapp on  http://maymaomao.shinyapps.io/devpro







