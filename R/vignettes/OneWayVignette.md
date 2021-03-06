---
title: "Statistics for Social Science"
author: "Craig A. Wendorf"
date: "2020-02-28"
output: 
  rmarkdown::html_vignette:
    keep_md: TRUE
vignette: >
  %\VignetteIndexEntry{One Way ANOVA}
  %\VignetteEngine{knitr::rmarkdown}
  %\VignetteEncoding{UTF-8}
---



## One Way ANOVA

### Enter Data


```r
Factor <- c(rep(1,4),rep(2,4),rep(3,4))
Outcome <- c(0,0,3,5,4,7,4,9,9,6,4,9)
Factor <- factor(Factor,levels=c(1,2,3))
OneWayData <- data.frame(Factor,Outcome)
OneWayData
```

```
##    Factor Outcome
## 1       1       0
## 2       1       0
## 3       1       3
## 4       1       5
## 5       2       4
## 6       2       7
## 7       2       4
## 8       2       9
## 9       3       9
## 10      3       6
## 11      3       4
## 12      3       9
```

### Calculate One Way ANOVA


```r
Results <- aov(Outcome~Factor)
model.tables(Results,"means")
```

```
## Tables of means
## Grand mean
##   
## 5 
## 
##  Factor 
## Factor
## 1 2 3 
## 2 6 7
```

```r
summary(Results)
```

```
##             Df Sum Sq Mean Sq F value Pr(>F)  
## Factor       2     56      28   4.667 0.0407 *
## Residuals    9     54       6                 
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```
