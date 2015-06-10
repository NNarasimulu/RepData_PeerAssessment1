# Reproducible Research: Peer Assessment 1

Set working directory to a local Github location for RepData_PeerAssessment1.

```r
setwd("C:/Users/NNarasim/Git/RepData_PeerAssessment1")
library(data.table)
```

## Loading and preprocessing the data
This reads the contents of the CSV file and removes all NA records.

```r
unzip ("activity.zip")
activity <- read.csv("activity.csv")
activity <- activity[complete.cases(activity),]
```



## What is mean total number of steps taken per day?
Aggregate the steps for each day to display in a histogram.

```r
activity_steps <- aggregate(steps ~ date, activity, sum)
hist(activity_steps$steps, xlab = "Total steps per day", ylab = "Number of occurences",
     main = "Total number of steps per day")
```

![](PA1_template_files/figure-html/hist-1.png) 

```r
act_mean <- mean(activity_steps$steps)
act_mean
```

```
## [1] 10766.19
```

```r
act_med <- median(activity_steps$steps)
act_med
```

```
## [1] 10765
```


## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
