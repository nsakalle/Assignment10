# Assignment 10
Nimish Sakalle  
NOvember 19, 2016  
  

```r
## The first step is to load R libraries that are required for the analysis.

library(plyr)
library(ggplot2)
library(knitr)
```
###**Making environment ready**


###** Reading from file into data frame **


```
## [1] "Age"         "Gender"      "Impressions" "Clicks"      "Signed_In"
```

```
##   Age Gender Impressions Clicks Signed_In
## 1  36      0           3      0         1
## 2  73      1           3      0         1
## 3  30      0           3      0         1
## 4  49      1           3      0         1
## 5  47      1          11      0         1
## 6  47      0          11      1         1
```

```
## 'data.frame':	458441 obs. of  5 variables:
##  $ Age        : int  36 73 30 49 47 47 0 46 16 52 ...
##  $ Gender     : int  0 1 0 1 1 0 0 0 0 0 ...
##  $ Impressions: int  3 3 3 3 11 11 7 5 3 4 ...
##  $ Clicks     : int  0 0 0 0 0 1 1 0 0 0 ...
##  $ Signed_In  : int  1 1 1 1 1 1 0 1 1 1 ...
```

```
## [1] 458441
```

###** Creating data grouping into variable AgeGroup **

```
##   Age Gender Impressions Clicks Signed_In Agegroup
## 1  36      0           3      0         1    35-44
## 2  73      1           3      0         1      65+
## 3  30      0           3      0         1    25-34
## 4  49      1           3      0         1    45-54
## 5  47      1          11      0         1    45-54
## 6  47      0          11      1         1    45-54
```
###** CReating subset for Impression >0 **

```
##   Age Gender Impressions Clicks Signed_In Agegroup
## 1  36      0           3      0         1    35-44
## 2  73      1           3      0         1      65+
## 3  30      0           3      0         1    25-34
## 4  49      1           3      0         1    45-54
## 5  47      1          11      0         1    45-54
## 6  47      0          11      1         1    45-54
```
###** New variable Click Through Rate **

```
##   Age Gender Impressions Clicks Signed_In Agegroup        CTR
## 1  36      0           3      0         1    35-44 0.00000000
## 2  73      1           3      0         1      65+ 0.00000000
## 3  30      0           3      0         1    25-34 0.00000000
## 4  49      1           3      0         1    45-54 0.00000000
## 5  47      1          11      0         1    45-54 0.00000000
## 6  47      0          11      1         1    45-54 0.09090909
```
###** Analysis of Click Stream  **
###** gPlot distributions of number impressions and click-through-rate (CTR = click/impression) for the age groups**
![](Assignment_10_files/figure-html/unnamed-chunk-6-1.png)<!-- -->
###** new variable CTR Behavior**

```
##   Age Gender Impressions Clicks Signed_In Agegroup CTR
## 1  36      0           3      0         1    35-44 <.2
## 2  73      1           3      0         1      65+ <.2
## 3  30      0           3      0         1    25-34 <.2
## 4  49      1           3      0         1    45-54 <.2
## 5  47      1          11      0         1    45-54 <.2
## 6  47      0          11      1         1    45-54 <.2
```
###**Subset for male and Female and sum of Impression, CLicks and Signed_In**

```
## [1] 167146
```

```
## [1] 288229
```

```
## [1] 2295559
```

```
## [1] 42449
```

```
## [1] 319198
```
###**Mean of Age, Impressions, CLicks, and percentage of males and Signed_In**

```
## [1] 29.48401
```

```
## [1] 0.09321768
```

```
## [1] 5.04103
```

```
## [1] 0.7009564
```
###**Mean of Age, Impressions, CLicks, and percentage of males and Signed_In by Age Group**

```
##   Group.1         x
## 1     <18  1.974572
## 2   18-24 21.268493
## 3   25-34 29.503573
## 4   35-44 39.493195
## 5   45-54 49.492928
## 6   55-64 59.497459
## 7     65+ 72.988409
```

```
##   Group.1          x
## 1     <18 0.14167788
## 2   18-24 0.04880905
## 3   25-34 0.05081227
## 4   35-44 0.05202148
## 5   45-54 0.05062260
## 6   55-64 0.10246952
## 7     65+ 0.15233226
```

```
##   Group.1        x
## 1     <18 5.033534
## 2   18-24 5.043240
## 3   25-34 5.026055
## 4   35-44 5.054749
## 5   45-54 5.045172
## 6   55-64 5.053484
## 7     65+ 5.046925
```

```
##   Group.1         x
## 1     <18 0.1231528
## 2   18-24 1.0000000
## 3   25-34 1.0000000
## 4   35-44 1.0000000
## 5   45-54 1.0000000
## 6   55-64 1.0000000
## 7     65+ 1.0000000
```

###** Create a table of CTRGroup vs AgeGroup counts **

```
##        
##            <18  18-24  25-34  35-44  45-54  55-64    65+
##   <.2   148412  34540  56980  69424  62936  43147  27261
##   .2-.4   5735    391    689    820    776   1104   1108
##   .4-.6    918     68    106    118    113    168    156
##   .6-.8     76      2      7      4      0      7     10
##   >.8      162     13     19     28     20     36     21
```
##** Histogram of Clicks by ageGroup **
![](Assignment_10_files/figure-html/unnamed-chunk-12-1.png)<!-- -->
###EOF###
