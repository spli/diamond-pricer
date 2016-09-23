---
title       : Diamond Pricer
subtitle    : Effectively pricing diamonds using linear modelling
author      : Simon Frost
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
--- .class #id

## Intro

Diamond Pricer is a quick and easy application to price your diamonds based on their cut, colour and clarity built on Shiny and R technology using statistical modelling. We use the diamonds dataset from ggplot2.


```
##   carat       cut color clarity depth table price    x    y    z
## 1  0.23     Ideal     E     SI2  61.5    55   326 3.95 3.98 2.43
## 2  0.21   Premium     E     SI1  59.8    61   326 3.89 3.84 2.31
## 3  0.23      Good     E     VS1  56.9    65   327 4.05 4.07 2.31
## 4  0.29   Premium     I     VS2  62.4    58   334 4.20 4.23 2.63
## 5  0.31      Good     J     SI2  63.3    58   335 4.34 4.35 2.75
## 6  0.24 Very Good     J    VVS2  62.8    57   336 3.94 3.96 2.48
```

--- 

## Getting the right price is very important

![plot of chunk unnamed-chunk-1](assets/fig/unnamed-chunk-1-1.png)

---

## A quick plot

Carat, clarity and cut are good predictors, and should be easy to fit a linear model.

![plot of chunk unnamed-chunk-2](assets/fig/unnamed-chunk-2-1.png)

---

## The model

We fit the following model, taking into account relationship between carat and price:

```
lm((log(price)) ~ I(carat^(1/3)) + carat + cut + clarity, data = diamonds)
```

---

## The Result

[https://spli.shinyapps.io/DiamondPricer/]

Please click and give it a go!

