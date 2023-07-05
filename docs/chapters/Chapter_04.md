## Aim of the lesson
After learning about literacy programming in Chapter 1 and Chapter 2, and Rmarkdown methods in Chapter 3. In this chapter, we will finally put together what we've learned to create a thorough final report, article, or other output that complies with the FAIR principle. To do this, we'll use the Quarto tool, which enables us to use the Rmarkdown syntax to easily blend coding and programming within the same text.
 

## Why using Quarto?

The pressure on scientific personnel to produce reports for public, governmental, and scientific audiences is rising. 
This takes a long time because you'll need to use several different applications to write, analyze data, make tables and figures, and so on.
Learning effective tools that integrate programming with report generation is crucial for streamlining this process. The markdown-based Quarto report framework, which is second-generation, provides an answer.
The ability to run code for data formatting, analysis, and visualization makes it possible for researchers to produce reports with minimal effort, all while writing in the familiar markdown format.


## Introduction
This lesson will use as an example the analysis of the **Wisconsin breast cancer data** (available [here](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)). The first usage of this data was described in @Streetetal1993.

# The header yaml

## Setting up the document

::: columns
::: {.column width="32%"}
``` yaml
---
title: "Document title"
author: "Your Name"
execute:
  echo: false
format: html
--- 
```

``` yaml
---
title: "Document title"
author: "Your Name"
execute:
  echo: false
format: pdf
--- 
```

``` yaml
---
title: "Document title"
author: "Your Name"
execute:
  echo: false
format: revealjs
--- 
```
:::

::: {.column width="10%"}
:::

::: {.column width="58%"}
-   Set up important document settings
-   Changing format is easy
    -   some settings might not work
-   Many more options
    -   some depending on output format
    -   some depending on template
:::
:::

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
