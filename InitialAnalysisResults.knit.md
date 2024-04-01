---
title: "Initial Project Report"
author: "Group 2"
date: "2024-03-08"
output:
  pdf_document: default
  html_document: default
---



#1 Introduction

Sejin Paik is a graduate student in the Boston University College of Communication Division of Emerging Media Studies. In a pilot study, Reframing the News Through Social Media Curation Design, she aims to explore the potential impacts of social media feed curation on users’ perceptions of news items and use the results to help with dissertation. Her research questions were the following: 
How does the activism feed affect perceptions of news credibility compared to the other surrounding-content newsfeeds?
How does the advertisement feed affect perceptions of a) news credibility, b) newsworthiness and c) shareworthiness of the news compared to the other surrounding-content newsfeeds?
How does news valence moderate the impact of external content elements on a) news credibility, b) newsworthiness, and c) shareworthiness? 
How do perceptions of news credibility, newsworthiness and shareworthiness in different curated newsfeeds vary between American and Chinese participants? 
From those questions, she formulated two main hypotheses. 
Memes will produce a greater level of a) credibility, b) newsworthiness, and c) shareworthiness perceptions of the news compared to the news-only newsfeed.
Activism will produce a greater level of a) newsworthiness and b) shareworthiness perception of the news compared to the other content surrounding newsfeeds.

Sejin’s data came from two different samples. The first sample was composed of 661 participants from the United States and the second sample was composed of 484 participants from China. Participants in both samples were randomly assigned to one of eight conditions according to a 4 by 2 factorial design. There were two independent variables, one with four levels and a second with two levels. The first independent variable was feed content type, which was one of the following: activism, advertisements, memes, and news. The second independent variable was story valence, which was either positive or negative. She also provided a copy of the manuscript for her paper, which included some of her background research and hypotheses, a copy of the survey that was distributed to the participants, and the SPSS output for her analyses.

Each newsfeed condition consists of seven posts: a positive or negative news story positioned fourth in the vertical newsfeed stack, surrounded by one of four content elements (memes, ads, activism, or additional news stories). The feeds were presented with topic filtering to reduce potential confounding variables and the topic is about artificial intelligence (AI), a relatively politically neutral subject.

The client requested assistance with a few tasks. First, she requested a duplication of ANOVA and ANCOVA tests that were performed to test her hypotheses to ensure that accurate results were obtained. Second, she requested that the results of the assumption checking be verified, as well as assistance with potentially modifying the analysis depending on whether the appropriate assumptions were met. Third, she asked that if there any potentially alternative or additional methods of analysis that might be more appropriate to answer her hypotheses and research questions, that those be recommended to her.

# Packages

```
## Warning: package 'readr' was built under R version 4.3.2
```

```
## 
## Attaching package: 'dplyr'
```

```
## The following objects are masked from 'package:stats':
## 
##     filter, lag
```

```
## The following objects are masked from 'package:base':
## 
##     intersect, setdiff, setequal, union
```

```
## Loading required package: carData
```

```
## 
## Attaching package: 'car'
```

```
## The following object is masked from 'package:dplyr':
## 
##     recode
```

```
## Warning: package 'ggplot2' was built under R version 4.3.2
```

```
## 
## Attaching package: 'gridExtra'
```

```
## The following object is masked from 'package:dplyr':
## 
##     combine
```

# Data loading

```
## Rows: 484 Columns: 351
## -- Column specification --------------------------------------------------------
## Delimiter: ","
## chr   (8): StartDate, EndDate, IPAddress, RecordedDate, ResponseId, Distribu...
## dbl (324): Status, Progress, Durationinseconds, Finished, LocationLatitude, ...
## lgl  (19): RecipientLastName, RecipientFirstName, RecipientEmail, ExternalRe...
## 
## i Use `spec()` to retrieve the full column specification for this data.
## i Specify the column types or set `show_col_types = FALSE` to quiet this message.
## Rows: 673 Columns: 403
## -- Column specification --------------------------------------------------------
## Delimiter: ","
## chr  (14): Date, EndDate, IPAddress, RecordedDate, ResponseId, DistributionC...
## dbl (367): Status, Progress, Durationinseconds, Finished, LocationLatitude, ...
## lgl  (22): RecipientLastName, RecipientFirstName, RecipientEmail, ExternalRe...
## 
## i Use `spec()` to retrieve the full column specification for this data.
## i Specify the column types or set `show_col_types = FALSE` to quiet this message.
```

#2 Data preparation
The surveys were administered to participants via Qualtrics and delivered to the consulting group as two separate .csv files, one for the American sample and one for the Chinese sample. They both contained variables such as the feed content and valence conditions the participants were assigned to, ratings of news credibility, ratings of newsworthiness, and ratings of news shareworthiness.

One of the main steps required as part of the data preparation was standardizing the labels for the main variables of interest in the data, since there were some labeling discrepancies between the two datasets. A second step involved changing certain variables to the appropriate data classes. For example, the “valence” variable had to be changed from numeric to factor. The next step was to filter the relevant variables for the analysis from each of the datasets to include in the analysis; both sets included hundreds of columns, many of which were unrelated to the relevant objectives. The final step involved combining the American and Chinese datasets to form a cohesive dataset that would allow for the analysis to be performed.




#3 Analysis


```
## Warning: Removed 116 rows containing non-finite values (`stat_boxplot()`).
## Removed 116 rows containing non-finite values (`stat_boxplot()`).
```

![](InitialAnalysisResults_files/figure-latex/plots-1.pdf)<!-- --> 

```
## Warning: Removed 115 rows containing non-finite values (`stat_ydensity()`).
```

```
## Warning: Groups with fewer than two data points have been dropped.
```

```
## Warning: Removed 115 rows containing non-finite values (`stat_ydensity()`).
```

```
## Warning: Groups with fewer than two data points have been dropped.
```

![](InitialAnalysisResults_files/figure-latex/plots-2.pdf)<!-- --> 

```
## Warning: Removed 116 rows containing non-finite values (`stat_ydensity()`).
```

```
## Warning: Removed 116 rows containing non-finite values (`stat_ydensity()`).
```

![](InitialAnalysisResults_files/figure-latex/plots-3.pdf)<!-- --> 


# Hypothesis 2
Activism will produce a greater level of:
  a) Newsworthiness
  b) Share-worthiness
Compared with the other 3 feeds.

This hypothesis was originally tested with ANCOVAs, with the feed content types and valences treated as independent variables and the following items as covariates: participants' frequency of sharing news posts on social media, attitudes on technology's impact (positive or negative) on society, and feelings toward AI automation. However, the client requested that the assumptions for these tests be repeated in order to make sure that these tests were appropriate.

## Hypothesis 2 Assumption checks

The first assumption to be checked was the normality of residuals.This assumption was for the Chinese and English datasets individually, since the client ran the tests on each sample separately; these assumption checks were repeated. The assumption was also checked for the combined dataset, since it is appropriate to check given that the data for the two groups were capable of being combined and the pertinent hypothesis does not explicitly reference a distinction between the two groups. The assumption was also checked for the Credibility measure, since this is required for some of the tests performed later in the analysis.First, visuals were created:




![](InitialAnalysisResults_files/figure-latex/normality plots-1.pdf)<!-- --> ![](InitialAnalysisResults_files/figure-latex/normality plots-2.pdf)<!-- --> ![](InitialAnalysisResults_files/figure-latex/normality plots-3.pdf)<!-- --> 

As is shown in the plots above,the residuals look skewed in opposite directions for the English and Chinese datasets for all three outcomes of interest. However, they appear uniformly distributed when the data are combined. Next, normality of the dependent variables was formally tested with the Shapiro-Wilk Test.

```
## 
## 	Shapiro-Wilk normality test
## 
## data:  res_cred_CN$residuals
## W = 0.97264, p-value = 7.286e-08
```

```
## 
## 	Shapiro-Wilk normality test
## 
## data:  res_NW_CN$residuals
## W = 0.96047, p-value = 4.101e-10
```

```
## 
## 	Shapiro-Wilk normality test
## 
## data:  res_SW_CN$residuals
## W = 0.97264, p-value = 7.286e-08
```

```
## 
## 	Shapiro-Wilk normality test
## 
## data:  res_cred_EN$residuals
## W = 0.98423, p-value = 9.945e-06
```

```
## 
## 	Shapiro-Wilk normality test
## 
## data:  res_NW_EN$residuals
## W = 0.96324, p-value = 1.395e-10
```

```
## 
## 	Shapiro-Wilk normality test
## 
## data:  res_SW_EN$residuals
## W = 0.98423, p-value = 9.945e-06
```

```
## 
## 	Shapiro-Wilk normality test
## 
## data:  res_cred_Data$residuals
## W = 0.98176, p-value = 3.888e-10
```

```
## 
## 	Shapiro-Wilk normality test
## 
## data:  res_NW_Data$residuals
## W = 0.97594, p-value = 4.065e-12
```

```
## 
## 	Shapiro-Wilk normality test
## 
## data:  res_SW_Data$residuals
## W = 0.98176, p-value = 3.888e-10
```


Another assumption that had to be checked was the homogeneity of variance. Levene's Test was performed to verify that this assumption holds true across the four feed conditions and the two valence conditions; it was applied for both the English and Chinese datasets, to replicate what the client did, and also for the combined data, to help inform the next steps for analysis.


```
## Levene's Test for Homogeneity of Variance (center = median)
##        Df F value Pr(>F)
## group   3  1.4586 0.2249
##       553
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##        Df F value Pr(>F)
## group   3  0.5177 0.6703
##       480
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##         Df F value Pr(>F)
## group    3   1.121 0.3395
##       1037
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##        Df F value   Pr(>F)   
## group   3  4.8969 0.002285 **
##       553                    
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##        Df F value Pr(>F)
## group   3  1.8656 0.1345
##       480
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##         Df F value Pr(>F)
## group    3  0.3375 0.7982
##       1037
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##        Df F value  Pr(>F)  
## group   3  3.6119 0.01321 *
##       553                  
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##        Df F value Pr(>F)
## group   3  1.3355 0.2621
##       480
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##         Df F value Pr(>F)
## group    3  1.0934 0.3509
##       1037
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##        Df F value   Pr(>F)    
## group   1  36.552 2.73e-09 ***
##       555                     
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##        Df F value Pr(>F)
## group   1  0.8978 0.3438
##       482
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##         Df F value    Pr(>F)    
## group    1  61.111 1.318e-14 ***
##       1039                      
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##        Df F value Pr(>F)
## group   1  0.2865 0.5927
##       555
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##        Df F value Pr(>F)
## group   1   8e-04 0.9781
##       482
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##         Df F value Pr(>F)
## group    1   1.248 0.2642
##       1039
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##        Df F value    Pr(>F)    
## group   1  14.044 0.0001973 ***
##       556                      
## ---
## Signif. codes:  0 '***' 0.001 '**' 0.01 '*' 0.05 '.' 0.1 ' ' 1
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##        Df F value Pr(>F)
## group   1  1.2809 0.2583
##       482
```

```
## Levene's Test for Homogeneity of Variance (center = median)
##         Df F value Pr(>F)
## group    1  0.4065 0.5239
##       1040
```

The Levene's Tests yielded mixed results. The test fails for a majority of the variables with the English dataset, with the exception of the newsworthiness across content feed types and shareworthiness between the two valence types. The tests passed across all variables for the Chinese dataset. The tests also passed across all variables for the combined dataset, with the exception of the assumption of homogeneity of variance for newsworthiness between the two valence conditions. 

#4 Conclusions

The assumptions for the tests utilized were not met in all cases. Assumptions of normality for the outcomes of interest were not met. When the tests were replicated for each of the two samples separately, they failed for all outcome variables of interest;they also failed across all variables when the data was aggregated. Assumptions of homogeneity were not met for several of the variables of interest. The analysis replicated the findings of the client in terms of the English dataset. This means that alternative tests are required for some of the hypothesis testing and to answer the research questions appropriately.


