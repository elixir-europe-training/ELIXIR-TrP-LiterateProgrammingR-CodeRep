# Aim of the lesson 
We will learn how to create and customize documents, articles, or reports that combine narrative text and code. We will use the Quarto tool to build our document and generate various output formats, including HTML, PDF, and Presentations. 

After covering literacy programming in Chapter 1 and Chapter 2, as well as Rmarkdown methods in Chapter 3, this chapter focuses on integrating our knowledge to create a comprehensive final report, article, or other outputs that adhere to the FAIR principle. To accomplish this, we will utilize the Quarto tool, which allows us to seamlessly combine coding and programming within the same text using Rmarkdown syntax.
The demand for scientific personnel to generate reports for public, governmental, and scientific audiences is increasing. However, this process often consumes a significant amount of time due to the need to use multiple applications for writing, data analysis, table and figure creation, and more. It is essential to learn effective tools that integrate programming with report generation in order to streamline this workflow. Quarto, a markdown-based report framework of the second generation, offers a solution. Researchers can leverage its ability to execute code for data formatting, analysis, and visualization, enabling them to produce reports with minimal effort while writing in the familiar markdown format.

## Prerequisites 
Before proceeding with this tutorial, it is recommended to have a basic understanding of R programming and familiarity with RStudio. Some knowledge of R Markdown syntax would also be beneficial.

## Prior Knowledge Assumed
This tutorial assumes that you are familiar with the following concepts:

- Basic R programming
- RStudio and its interface
- Markdown syntax and document rendering

## Why Use Quarto? 
This tutorial introduces Quarto, an **open-source** publishing system based on Pandoc. Quarto is the next generation of RMarkdown, offering support for dynamic and static documents and multiple programming languages. With Quarto, you can effortlessly combine narrative text and code to create various resources like documents, books, presentations, web pages, and more. Quarto is a command line interface (CLI) that renders plain text formats (.qmd, .rmd, .md) OR mixed formats (.ipynb/Jupyter notebook) into static:
- PDF
- MS Office (Word, Powerpoint)
- HTML reports
- Presentation (Powerpoint, Beamer, revealjs)
- Books
- Websites
- Journal articles

Summary:
- Easier to organize/structure document and document layout
- Features largely cross-format
- Better ability to integrate multiple languages in a PROJECT
- Evaluate native language (R in knitr, Python/Julia in Jupyter)
- HTML slides with revealjs are pandoc-compatible, so RStudio Visual Editor works with them

## Additional Resources 📚

If you want to explore more about Quarto and its capabilities, consider checking out the following resources:

- [Quarto documentation](https://quarto.org/docs/)
- [Pandoc](https://pandoc.org/)
- [R Markdown documentation](https://rmarkdown.rstudio.com/)
- [RStudio cheatsheets](https://rstudio.com/resources/cheatsheets/)

# Before Starting
## Installation Instructions ⚙️

- Install latest version of RStudio
- Install Quarto. Follow the installation instructions on the [Quarto webpages](https://quarto.org/)
- After installing Quarto, open the terminal in RStudio and Install/Update the following 📦:

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

When creating PDFs from Quarto, we must install LaTeX for that conversion. We will use the Tinytex package to install a lightweight LaTeX distribution on your computer.

Open RStudio, and find the section called “Console”.

```R
tinytex::install_tinytex()
tinytex:::install_yihui_pkgs()
```
## Example Dataset 📊

Throughout this tutorial, we will be using a sample dataset called "Wisconsin breast cancer data." Please make sure to download this dataset and save it in a location accessible to your R environment. You can download the dataset from [this link](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data). The first usage of this data was described in @Streetetal1993.

# Introduction
Quarto uses a two-step workflow to render documents. First, the .qmd file is sent to knitr (https://yihui.org/knitr/), which executes the code chunks and generates a markdown (.md) document with code and output. Then, pandoc (https://pandoc.org) processes the markdown file to create the final output file. This flexible process allows for a wide range of output formats. 

ADD FIGURE

## Let's Get Started!

Let's set up our environment and create a basic Quarto document. 

### Creating a Basic Quarto Document

To begin working with your own .qmd file, simply navigate to the menu bar and choose **File > New File > Quarto Document...** This action will trigger RStudio to open a wizard, which assists in automatically filling your file with helpful content that serves as a reminder of the fundamental functionalities of Quarto.

In the subsequent sections, we will delve deeper into the three main elements of a Quarto document: the markdown text, the code chunks, and the YAML header.


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

## Exercise 
Use RStudio to create a new default Quarto document
Add a title and your name as the author
Change format to html theme to sketchy
Add toc
Create two sections, one with fact you want to learn and your favorite thing about R
Render it with RStudio button, then try with the R package and terminal

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
