# Aim of the lesson 
The demand for scientific reports, documents, and articles is increasing, but the process often involves multiple applications and consumes significant time. Quarto, a second-generation markdown-based report framework, offers a solution. It allows researchers to execute code for data formatting, analysis, and visualization, streamlining report generation while writing in a familiar markdown format.

This Chapter will teach us how to create and customize documents, articles, or reports that combine narrative text and code. We will use the Quarto tool to build our document and generate various output formats, including HTML, PDF, and Presentations. We will combine our understanding of literacy programming and Rmarkdown methods to create thorough reports and articles that follow the FAIR principle. To accomplish this, we use the Quarto tool, which effortlessly blends coding and programming within the text using Rmarkdown syntax.

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
- Easier to organize/structure documents and document layout
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

# Let's Get Started!

## Quarto document: a practical overview
Instead of basic scripts, we use Quarto files in RStudio to make our workflow reproducible. Quarto files can dynamically generate our paper's code and story. A Quarto file's YAML header, Quarto-formatted text, and R code blocks (sometimes termed "code chunks") are its main components. A Quarto document is formed by three main elements: 

1. The YAML header

2. A Quarto text

3. R code chunks for embedded analysis

Finally, to render the document, we use the engine called _Knitr_


ADD FIGURE (with the process described above)


Let's set up our environment and start creating a basic Quarto document. 

## Creating a Basic Quarto Document

To begin working with your .qmd file, navigate to the menu bar and choose **File > New File > Quarto Document...** This action will trigger RStudio to open a wizard, which assists in automatically filling your file with helpful content that serves as a reminder of the fundamental functionalities of Quarto.

## 1. The header yaml (Metadata)
YAML metadata, or the header, is crucial to Quarto documents. This metadata is your document's backstage pass and influences many rendering phases. It contains crucial information that can shape your document's code, content, and presentation, placed at the beginning and carefully evaluated by Pandoc, Quarto, and knitr.

Quarto default YAML header includes the following metadata surrounded by three dashes ---:
- title
- author
- format
- editor

FIGURE showing the Yamal

``` yaml
---
title: "Document title"
author: "Your Name"
execute:
  echo: false
format: html
--- 
```

You can select one of three default formats as **format**: pdf, html, or word document. Essentially, this allows you to export your qmd file as a different file type. 

Other YAML formatting options include adding bibliography information, customizing output, and changing code execution defaults.

## 2. Text 
This is just markdown-formatted text narrative (more on markdown in Chapter 3). Plain text in Quarto is narrative text in the document. R scripts want plaintext to be code. In Quarto, code must be enclosed in special characters. Formatting symbols like ##, **, and < > are used instead of standard grammar components.

Example (need to fix this)
# Heading 1
This is a sentence with some **bold text**, some *italic text* and an [image](image.png).

For how to write the text see Chpater 3 in this tutorial

## 3. Code
In the qmd file, code blocks are marked in gray. On either side of them are three tick marks ('''), and when viewed in source mode, the first three tick marks are followed by curly brackets that contain other code. Beginning of code block denoted by tick marks; information between curly brackets specifies how R should interpret the code for display (more on this in the Knitr syntax series). The R code for things like summaries, analyses, tables, and graphs goes here. If you already have a R script developed, you can simply copy and paste it between the few lines of required formatting to embed it and run it wherever you choose in the document.

You can code in many different languages in RStudio: R, Phyton, Bash. SQL

## Code
```{r}
#| output-location: column
#| label: fig-airquality
#| fig-cap: Temperature and ozone level.
#| warning: false

library(ggplot2)

ggplot(airquality, aes(Temp, Ozone)) + 
  geom_point() + 
  geom_smooth(method = "loess"
)
```

FIGURE with a page containing both text and code 

### Rendering Qmd Document
Simply enough, rendering is moving material from one medium or file type to another that supports pages or pagination. When you click render, your code will be compiled, verified for faults, and written to the yaml header file type. When you save your modifications, click "Render on Save" to preview your document. It also checks code, so make sure your qmd document is error-free before expecting it to execute and render.

Give your document a name and pick a folder before rendering it. Name your file my_first_qmd.qmd and save it to an accessible file system directory.

FIGURE showing the bottom to be pressed for render 

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
