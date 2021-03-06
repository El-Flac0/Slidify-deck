---
title       : The Goal Machine
subtitle    : Predictors of Success in Soccer
author      : Andrew Laws, MSc.
job         : Economist
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## The Problem

“How many countries can you think of where a corner kick is treated with the same applause as a goal? One. It only happens in England.” - Jose Mourinho

* Perceived predictors of success in soccer may not actually be what they seem.
  + Numbers of corners are routinely used in TV reports to imply attacking intent, is that meaningful?
  + Do shots on target actually translate into more points?
  + Are teams more successful if they foul the opposition more or less often?

--- .class #id

## Measures of Success

"Goals are overrated" - Jonathan Wilson

* Users of the Goal Machine have the option to select between Mean Goals and Mean Points.
* Two metrics are success have been chosen as at any point in a match the aim is to score a goal;
* However, the aim of the match is win and secure the points, in this respect winning by one goal is the same as winning by six goals

--- .class #id

## The Goal Machine

"Efficacy is not divorced from beauty" - Luis Cesar Menotti

The Goal Machine works by allowing users to select a combination of the following:

* Select the stat of interest from the drop-down menu;
* Select whether Home matches, Away matches, or Home and Away matches should be included;
* Select from the drop-down menu a club that played one season in the premier league between 2000 - 2014;
* Finally, select the desired metric from mean goals and mean stats.

--- .class #id

## Linear Model

"It's all very simple, score more than your opponent and you win." - Johann Cryuff

* The Goal Machine is powered by a fairly straightforward Linear Model within the ggplot function:


```r
  g <- ggplot(eplSelect, aes_string(x=stat, y=metric, colour="Location")) + geom_point() + 
    geom_smooth(method=lm, se=FALSE, fullrange=TRUE) + 
    scale_colour_discrete(limits = levels(eplSelect$Location)) +
  print(g)
```

--- .class #id

## Demonstration

* In the following, the correlation between fouls committed and mean goals for Arsenal, Home and Away, 2000 - 2014 is returned.

<img src="./GoalMacDemo.png" height="450px" width="800px" />






