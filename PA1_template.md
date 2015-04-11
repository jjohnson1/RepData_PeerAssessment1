# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data
First, we load the data from the specified file:


```r
raw <- read.csv("activity.csv", header=T)
```

At this time, no preprocessing is performed.

## What is mean total number of steps taken per day?
Per the instructions, missing values are ignored at this step. I make use of 
the dplyr library for easier data manipulation.


```r
library(dplyr)
byDay <- raw %>% group_by(date) %>% summarize(total = sum(steps))
hist(byDay$total, xlab="Total Steps", ylab="Number of Days", main="Total Steps per Day")
```

![](PA1_template_files/figure-html/unnamed-chunk-2-1.png) 

```r
meanSteps <- mean(byDay$total, na.rm=T)
medianSteps <- median(byDay$total, na.rm=T)
```

From the code above, we learn that the mean number of steps per day is 1.0766189\times 10^{4} and the median is 10765.

## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
