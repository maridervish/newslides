---
title       : Russian foreign trade statistics
subtitle    : Presentation of Application
author      : Mari Dervish
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
--- bg:#EEE

## General information about application

If one needs to analyze Russian import/export data (for example to see how Russian food embargo affected trade volumes between countries), this application will show trade statistics in fast and easy way.

This application plots trade statistics between Russia and other countries for period Jan2014-Jun2015.
App is made in `shiny` package for `R`.
Application can be run on RStudio's shiny server: https://mdervish.shinyapps.io/myApp

Definetely there is room for significant improvement, but as it is a project for Coursera class, I decided to keep application easy. In the future I will add more features and data to use application in real life.

--- bg:#EEE

## How to use application

On the left panel of application:

> - Choose direction of trade flow (Import/Export)
> - Choose country you are interested in
> - Choose product category you are interested in

> - Then go to tab 'Result' where you will find plot of trade statistics between Russia and chosen country for chosen parameters.

--- bg:#EEE

## Data structure

Data is taken from open database of Russian Federal Customs Service.
To reduce time for loading application for this class data was limited for only TOP-30 countries-partners of Russia

Data structure:

```r
impex <- read.csv("./top.csv")
```

```
## Warning in file(file, "rt"): cannot open file './top.csv': No such file or
## directory
```

```
## Error in file(file, "rt"): cannot open the connection
```

```r
head(impex,3)
```

```
##   X        Country Year       Period TradeFlow       Commodity    Value
## 1 1         Sweden 2014   April 2014   Imports 01 Live animals  3414.35
## 2 2 Czech Republic 2014 October 2014   Imports 01 Live animals 25666.63
## 3 3          China 2014   March 2014   Imports 01 Live animals  2180.00
##         date
## 1 2014-04-01
## 2 2014-10-01
## 3 2014-03-01
```

--- bg:#EEE

## List of countries included

As it explained before, data contains information only about TOP-30 Russian trade partners.
List of countries:

```r
unique(impex$Country)
```

```
##  [1] Sweden         Czech Republic China          Belarus       
##  [5] Slovakia       France         Ukraine        Italy         
##  [9] Kazakhstan     Germany        Hungary        Netherlands   
## [13] United Kingdom Latvia         United States  Japan         
## [17] Belgium        Lithuania      Singapore      Poland        
## [21] Finland        Spain          Switzerland    Brazil        
## [25] Estonia        Turkey         South Korea    Taiwan        
## [29] India          Egypt         
## 30 Levels: Belarus Belgium Brazil China Czech Republic Egypt ... United States
```
