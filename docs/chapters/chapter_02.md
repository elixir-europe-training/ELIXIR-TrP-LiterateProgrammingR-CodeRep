## Introduction
This chapter is a gentle introduction to the literate programming approach, and a preview of the components that will be covered in the next few chapters. By the end of this chapter, it is hoped that you will find this approach useful and understand its basics.

## The Old Workflow
To begin with, let me ask you a couple of questions:

1. How do you usually organise your scripts and files when you conduct research?
2. What is your workflow of creating a deliverable (report, presentation slides, etc.) from these scripts?

### A likely answer
You may have the following files in a folder:

1. some raw data files (.csv)
2. a bunch of programming scripts (.R or .py)
3. some image files (.png, .jpg, etc.)
4. some plain text files (.tex)
5. some auxiliary files (.bib, .sty, subfolders)

And the workflow is like this:

1. run the scripts in an Integrated Development Environment (IDE),
2. save the required plots to the image files,
3. edit the plain text files (writing the explanatory text and inserting numbers and tables manually), and
4. generate the report or the slides you want.

If you are working with others, you are likely to collaborate through [Overleaf](https://www.overleaf.com/), and this means an extra step of uploading the files before the final step. Done and dusted.

### Changing the data / analysis
It is common that the analysis changes direction as you go along, and/or that the data is updated. When that happens, you re-run the scripts, save the image files, (optionally) upload them, and generate the deliverable again. And this is usually done multiple times and in an iterative fashion. One or more of the following scenarios eventually happens:

1. You have changed the analysis and edited the programming scripts on your computer, but have not updated the results (plots, numbers, tables) in the plain text files. When you revisit the deliverable after some time, the results reported do not match what you get from running the scripts.
2. You have decided to change the analysis to a previous direction, but because the scripts have been updated, you cannot revert exactly to what you want.
3. To avoid the above scenario, you create a new set of programming scripts every time you change the analysis. Eventually it becomes difficult to find the right version (again).

If you feel dissatisfied with this workflow, you will benefit from this training programme. You will be able to adopt a more efficient workflow that not only generates a deliverable with reproducible results, but also keeps track of the versions of the files so there won't be anything like `presentation-final-final-02.pdf`.

## Literate Programming
Practically, literate programming (almost) means merging the .R/.py and .tex files in the old workflow. Let's start with a snippet of an R script:

```
cancer_data <- read.csv("breast-cancer-wisconsin/data.csv") # load the data
head(cancer_data) # print the first few lines
dim(cancer_data) # the dimensions
colnames(cancer_data) # column names
```

It is an acceptable practice to comment the code so others, including your future self, will understand the analysis. However, the comments make the code more difficult to read as the analysis expands, and it is better to have the code and the text that explains the analysis (called the prose hereafter) in separate sections, but still in the same file. This *is* the essence of literate programming.

### First pass
Let's try to separate the code and prose in the same file in the most naive way:

```
We first load the Wisconsin breast cancer data:
cancer_data <- read.csv("breast-cancer-wisconsin/data.csv")
Then we print the first few lines, the dimensions and the column names, using the following three commands respectively:
head(cancer_data)
dim(cancer_data)
colnames(cancer_data)
```

You will immediately come up with questions: 

1. How does someone else tell the code from the data?
2. This piece of code cannot be run as running the prose will return errors. Then what good does it do to me?

### Second pass
It is the worst of both worlds if neither a human nor a machine can understand the lines. Fortunately, standards and syntaxes have been created to make literate programming possible. This is how such a script looks like:

````
We first load the Wisconsin breast cancer data: 

```{r}
cancer_data <- read.csv("breast-cancer-wisconsin/data.csv")
```

Then we print the first few lines, the dimensions and the column names, using the following three commands respectively:

```{r}
head(cancer_data)
dim(cancer_data)
colnames(cancer_data)
```
````

We shall call any R code, together with the preceding line (triple backticks and `{r}`) and succeeding line (triple backticks) a *code chunk*. Code chunks will be an important concept throughout.

### Self-contained file
What you have seen above is just a snippet. A self-contained file will look like this:
````
---
title: "Analysis of Wisconson Breast Cancer Data"
date: "2023-06-06"
author: "CodeRep Literate Programming Team"
output: pdf_document
---

We first load the Wisconsin breast cancer data: 

```{r}
cancer_data <- read.csv("breast-cancer-wisconsin/data.csv")
```

Then we print the first few lines, the dimensions and the column names, using the following three commands respectively:

```{r}
head(cancer_data)
dim(cancer_data)
colnames(cancer_data)
```
````

### The components
This hybrid format starts to get confusing, as you may wonder what all those triple dashes, triple backticks, lines at the top etc. do. This is a good point to preview the next few chapters:

1. The syntax of the file, barring the code chunks, is in Markdown, which will be introduced in [next chapter](../chapter_03). If you have used LaTeX to write documents, Markdown is a similar (yet simpler) typesetting system. As we will see, it has a gentler learning curve and more functionality to offer.
2. The file format is called Quarto ([Chapter 4](../Chapter_04)), which facilitates the interweaving of code chunks and prose. When you save the file, the file extension is .qmd. 

## Reproducibility, and more

## I'm confused with all these terms
Don't worry, we've got you covered

- RStudio: primarily Integrated Development Environment (IDE) for R, but growing support for other languages (Julia, Python)
- Markdown: as a testament, these materials are written in Markdown
- Rmarkdown: essentially R + Markdown, generating results dynamically, thus guaranteeing reproducibility
- YAML: the definition is not very useful; essentially a preamble; similar to lines before `\begin{document}` in a .tex file
- Quarto: the next version of Rmarkdown i.e. R/Python/Julia etc. + Markdown

