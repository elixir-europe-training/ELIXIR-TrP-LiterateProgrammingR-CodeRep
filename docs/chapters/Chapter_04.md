## Aim of the Lesson 📚

After covering literacy programming in Chapter 1 and Chapter 2, as well as Rmarkdown methods in Chapter 3, this chapter focuses on integrating our knowledge to create a comprehensive final report, article, or other outputs that adhere to the FAIR principle. To accomplish this, we will utilize the Quarto tool, which allows us to seamlessly combine coding and programming within the same text using Rmarkdown syntax.

## Prerequisites ✅

Before proceeding with this tutorial, it is recommended to have a basic understanding of R programming and familiarity with RStudio. Some knowledge of R Markdown syntax would also be beneficial.

## Prior Knowledge Assumed

This tutorial assumes that you are familiar with the following concepts:

- Basic R programming
- RStudio and its interface
- R Markdown syntax and document rendering

## Why Use Quarto? 🔍

The demand for scientific personnel to generate reports for public, governmental, and scientific audiences is increasing. However, this process often consumes a significant amount of time due to the need to use multiple applications for writing, data analysis, table and figure creation, and more. It is essential to learn effective tools that integrate programming with report generation in order to streamline this workflow. Quarto, a markdown-based report framework of the second generation, offers a solution. Researchers can leverage its ability to execute code for data formatting, analysis, and visualization, enabling them to produce reports with minimal effort while writing in the familiar markdown format.

## Additional Resources 📚

If you want to explore more about Quarto and its capabilities, consider checking out the following resources:

- [Quarto documentation](https://quarto.org/docs/)
- [R Markdown documentation](https://rmarkdown.rstudio.com/)
- [RStudio cheatsheets](https://rstudio.com/resources/cheatsheets/)## Additional Resources 📚


# Before Starting

## Installation Instructions ⚙️

To install Quarto, you can take a look at the [Quarto webpages](https://quarto.org/) for the installation instructions.

## R Packages 📦

To ensure the necessary functionality, run the following code in R:

```R
# Run in R
install.packages(c(
  "tinytex",       # for PDF rendering
  "rmarkdown",     # rendering everything
  "tidyverse",     # data-wrangling
  "knitr",         # table printing
  "kableExtra"    # table printing
))
```

When creating PDFs from Quarto, we need to install LaTeX for that conversion. We will use the tinytex package to install a lightweight LaTeX distribution on your computer.

Open RStudio, and find the section called “Console”.

```R
tinytex::install_tinytex()
tinytex:::install_yihui_pkgs()
```

# Introduction
## Example Dataset 📊

Throughout this tutorial, we will be using a sample dataset called "Wisconsin breast cancer data." Please make sure to download this dataset and save it in a location accessible to your R environment. You can download the dataset from [this link]((https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data). The first usage of this data was described in @Streetetal1993.


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
