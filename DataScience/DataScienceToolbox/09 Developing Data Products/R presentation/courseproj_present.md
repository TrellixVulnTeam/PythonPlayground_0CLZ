Stock index investigator
========================================================
author: Lai Yiu Ming
date: 9 Jul, 2015

What this application does?
========================================================

This application shows the distribution of daily return and daily volume of the two markets in the form of histogram.

- NASDAQ Composite, United State
- Hang Seng Index, Hong Kong


How data comes from?
========================================================

The data is downloaded from Yahoo Finance! For this application, the preprocess data is place on the dropbox.

For NASDAQ Composite

```r
library(ggplot2)
datasetIXIC <- read.csv("https://www.dropbox.com/s/rqt6gk0vrdylehe/nasdaq.csv?dl=1")
```

For Hang Seng Index

```r
datasetHSI <- read.csv("https://www.dropbox.com/s/25joq3q1wf3yunx/hsi.csv?dl=1")
```

Daily Return
========================================================
Daily return is calcuated by daily adjusted close price.

Daily return = (adjusted close price of current day / adjusted close price of previous trading day) - 1


```r
p <- ggplot(datasetHSI, aes(DailyReturn)) + geom_histogram()
print(p)
```

![plot of chunk unnamed-chunk-3](courseproj_present-figure/unnamed-chunk-3-1.png) 

Daily Volume
========================================================
Daily volume is taken directly from Yahoo! Finance


```r
p <- ggplot(datasetHSI, aes(DailyVolume)) + geom_histogram()
print(p)
```

![plot of chunk unnamed-chunk-4](courseproj_present-figure/unnamed-chunk-4-1.png) 
