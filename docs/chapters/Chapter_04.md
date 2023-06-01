## Why using Quarto?

The pressure on scientific personnel to produce reports for public, governmental, and scientific audiences is rising. 
This takes a long time because you'll need to use several different applications to write, analyze data, make tables and figures, and so on.
Learning effective tools that integrate programming with report generation is crucial for streamlining this process. The markdown-based Quarto report framework, which is second-generation, provides an answer.
The ability to run code for data formatting, analysis, and visualization makes it possible for researchers to produce reports with minimal effort, all while writing in the familiar markdown format.

## Aim of the lesson

## Introduction
This lesson will use as an example the analysis of the **Wisconsin breast cancer data** (available [here](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)). The first usage of this data was described in @Streetetal1993.

## Upload needed packages  
Before looking at the data:

-   we load the packages required

```{r}
#| label: load-packages
#| include: false

library(tibble) # Provides a modern, tidy alternative to data frames.
library(dplyr)  # data manipulation
library(readr)  # reading csv file data 
library(ggplot2)# plotting system
library(caret)
library(ROCR)   # evaluating and visualizing the performance of binary classifiers
library(pROC) # r evaluating and visualizing the performance of binary and multi-class classifiers using Receiver Operating Characteristic (ROC) analysis.
theme_set(theme_bw(12))
knitr::opts_chunk$set(fig.align = "center")
```
-   set the theme of the plots using `theme_set()` in package `ggplot2` [@Wickham2016].


```{r}
#| label: load-packages
#| include: false

theme_set(theme_bw(12))
knitr::opts_chunk$set(fig.align = "center")
```
