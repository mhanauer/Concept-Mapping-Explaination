# Concept-Mapping-Explaination
---
title: "Bayes Loop Results"
output:
  pdf_document: default
  html_document: default
---

```{r setup, include=FALSE}
knitr::opts_chunk$set(echo = TRUE)
```
Library the packages
```{r}
library(MCMCpack)
library(descr)
library(ggplot2)
library(psych)

library(MASS)
library(cluster)
library(factoextra)
library(ggpubr)
library(tidyverse)
```
Now load the data
We get the distance by taking using this formula: http://rosalind.info/glossary/euclidean-distance/

sqrt(x2-x1)^2+(y2-y1)^2...+(z2-z1)^2) for each variable in the data set.  Then for column in the distance matrix the difference between two and three for each variable and so on. 

Differences between linkages: https://nlp.stanford.edu/IR-book/completelink.html

Single: Merge the two clusters with the least distance (choose distance)
Complete: See this example: https://newonlinecourses.science.psu.edu/stat555/node/86/
```{r}
setwd("C:/Users/Matthew.Hanauer/Desktop")
datTest = read.csv("datCorMD.csv", header = TRUE)
head(datTest)
get_dist(datTest)

datTest2 = datTest[,1:2]
get_dist(datTest2)

sqrt((4-10)^2+(10-4)^2)

sqrt((5-4)^2+(9-10)^2)


datTest3 = datTest[,1:3]
get_dist(datTest3)
sqrt((4-10)^2+(10-4)^2+(9-5)^2)

```
For a denogram you take each pair of items then you get the distance (use eliccian) for each pair of points and whichever pair is the lowest, we combine those two and either take the average of the points or take the min value of the two points.  Items must be on the same scale. Keep going until all items are in the same cluster.  Find the point that best fits the data

Example: https://people.revoledu.com/kardi/tutorial/Clustering/Online-Hierarchical-Clustering.html
```{r}
sqrt((3-3)^2+ (3.5-4)^2 + (5-5)^2)

```



