## 4.1 What's Our Goal? 🎯

**Objective:** This lesson's mission is to make your life easier by introducing Quarto, a modern markdown-based report framework. We'll show you how Quarto streamlines the creation of scientific reports, documents, and articles by combining code execution for data formatting, analysis, and visualization with simple markdown.

## 4.2 What is Quarto, and Why Does It Matter? 📖

[Quarto](https://quarto.org/) isn't just another R package; it's the future of RMarkdown. It's an open-source publishing system, powered by Pandoc, that's designed to work with multiple programming languages like Python and Julia. Quarto simplifies the entire R Markdown ecosystem, allowing you to effortlessly mix text and code for various purposes, including documents, books, presentations, web pages, and more.

**Key Benefits of Quarto:**
- Streamlined document organization and layout.
- Seamless integration across different formats.
- Enhanced support for multiple programming languages within a single project.
- Native language execution (e.g., R in knitr, Python/Julia in Jupyter).
- Compatibility with RStudio Visual Editor for creating HTML slides.

## 4.4 Before We Begin 🛠️

### 4.4.0 Installation Instructions ⚙️

Before diving in, let's ensure you have the necessary tools at your fingertips:

1. **RStudio:** Make sure you have the latest version of RStudio installed.

2. **Quarto:** Follow the installation instructions on the [Quarto website](https://quarto.org/).

3. Once Quarto is installed, open RStudio's terminal and install/update the following R packages using this command:

```R
# Run in R
install.packages(c(
  "tinytex",       # Needed for PDF rendering
  "rmarkdown",     # Essential for rendering
  "tidyverse",     # Useful for data wrangling
  "knitr",         # Required for table printing
  "kableExtra"     # Enhances table printing
))
```

## 4.5 Let's Dive In! 🌊

### 4.5.1 The Quarto Workflow

Quarto operates on a two-step process to create documents. Here's how it works:

1. **Code Execution**: Your `.qmd` file is handed over to ![**knitr**](https://yihui.org/knitr/), which takes care of executing code chunks and generating a markdown (.md) document. This markdown file includes both code and its output.

2. **Final Rendering**: Next, ![**pandoc**](https://pandoc.org) steps in to process the markdown file, ultimately producing the final output. The beauty of this process is its flexibility—it supports a wide range of output formats.

*[Include a visual diagram of the Quarto workflow here]*

### 4.5.2 Understanding the Quarto Document

Instead of relying on plain scripts, we use Quarto files in RStudio to bring reproducibility into our workflow. Quarto files have the power to dynamically generate code and narratives for our documents. The key components of a Quarto document are:

1. **The YAML Header**: This acts as your document's backstage pass, influencing various rendering phases. It holds essential information that shapes your document's code, content, and presentation. The YAML header is placed at the beginning of your document and is carefully evaluated by Pandoc, Quarto, and knitr.

2. **Quarto-formatted Text**: Text in a Quarto document follows Markdown formatting rules. While regular text is fine for humans, **R scripts** need specific formatting to be interpreted as **code**. Quarto requires code to be enclosed in special characters and formatting symbols like `**##**`, `**\*\***`, and `**< >**` instead of standard grammar components.

3. **R Code Chunks**: Code blocks in a `.qmd` file are visually distinct with their gray background. Each code block is enclosed by three tick marks (`**'''**`). In source mode, the first three tick marks are followed by curly brackets containing additional code. These code blocks define the **R code** for tasks like generating summaries, conducting analyses, creating tables, and generating graphs. If you already have an R script, you can simply **copy and paste** it into the document, ensuring it adheres to the required formatting.

Quarto provides flexibility in coding by allowing you to use various languages within RStudio, including **R**, **Python**, **Bash**, and **SQL**.

**Example Code:**

```{r}
## ----read---------------------------------------------------------------------
cancer_data <- as_tibble(read.csv("data/breast-cancer-wisconsin.csv"))
head(cancer_data)
cancer_data$diagnosis <- as.factor(cancer_data$diagnosis)
colnames(cancer_data)
dim(cancer_data)
```

### 4.5.3 Creating Your First Quarto Document

![Screenshot of my chart](https://github.com/elixir-europe-training/ELIXIR-TrP-LiterateProgrammingR-CodeRep/blob/main/docs/chapters/Figure1.png)

*Figure A: A Quarto document in RStudio that combines code and results.*

Let's get started by creating a basic Quarto document:

#### 4.5.3.1 Starting a New Quarto Document 

In RStudio, follow these steps to begin:

1. Navigate to the menu bar and select **File > New File > Quarto Document...**.
2. RStudio will open a wizard to help you set up your document with essential content and configurations.

#### 4.5.3.2 YAML Header (Metadata)

The **YAML metadata**, or header, is absolutely essential in Quarto documents. This metadata acts as your document's backstage pass, influencing many rendering phases. It contains crucial information that shapes your document's code, content, and presentation. Placed at the beginning, the YAML header is carefully evaluated by Pandoc, Quarto, and knitr.

A default Quarto YAML header includes the following metadata surrounded by three dashes `---`:

- `title`
- `author`
- `format`
- `editor`

Here's an example YAML header:

```yaml
---
title: "Document title"
author: "Your Name"
execute:
  echo: false
format: html
---
```


### 4.5.4 Rendering Qmd Document

**Rendering** in Quarto is the process of converting your document from one format to another that supports pages or pagination. When you click render, your code will be compiled, verified for faults, and written to the YAML header file type. It also checks code for errors, so ensure your `.qmd` document is free of errors before proceeding.

To render your document:

1. Give your document a **name** and choose a **folder** for rendering.

   - Name your file `my_first_qmd.qmd`.
   - Save it to an accessible file system directory.

2. Click the **"Render"** button, usually located at the bottom of your interface (see the figure below).

**FIGURE:** [Insert an image or screenshot showing the "Render" button.]

<div class="exercise" style="background-color: #ffffcc; border: 1px solid #cccc00; padding: 10px;">

**Exercise**

1. Use **RStudio** to create a new default Quarto document.
2. Add a **title** to your document.
3. Specify your **name as the author**.
4. Change the **format** to **HTML**.
5. Finally, **render the document**.

</div>

### Solution

*[Provide screenshots of the solution here]*


## 4.5 Writing Quarto Documents

### RStudio Visual Editor: Simplified Formatting

The RStudio visual editor simplifies formatting, making it easier to create Quarto documents. To access the visual editor for your document, follow these steps:

1. **Activate Visual Mode**: Click the visual option at the top-left of the toolbar.

   This opens a formatting bar that resembles popular document editors like Google Docs.

2. **Switch Between Modes**: You can switch between source and visual modes at any time. This feature lets you retain your editing location and undo/redo your changes.

### *Writing text*

##### Adding Headings

To create headings, you can use a shortcut. For a list of editing shortcuts, refer to [this link](https://rstudio.github.io/visual-markdown-editing/shortcuts.html).

_Example:_
```markdown
# Heading 1
This is a sentence with some **bold text**, some *italic text*, and an ![image](image.png).
```

### *Creating Bullet and Numbered Lists*

In Quarto, you can easily transform plain text into organized lists. Here's how:

**Bullet Lists:**
- To create a bullet list, simply start each item with an asterisk (*), a plus (+), or a hyphen (-), followed by a space.

 Example:
   ```markdown
   - Item 1
   - Item 2
   - Item 3
```
  Example:
   ```markdown
1. First item
2. Second item
3. Third item
```
### *Adding Images*
You can enhance your Quarto documents by adding images. The visual editor simplifies this process:

**Browse and Insert**: Click on the image icon in the formatting bar, browse your computer to find the image file, and insert it into your Qmd document.
Example
```
![Alt Text](image.png)
```
### *Adding Links*
In Quarto, adding links is straightforward:

1. **Link Icon**: Click on the link icon in the formatting bar.
2. **Paste URL**: Paste the web address (URL) in the URL field.

Example:
```markdown
[Link Text](https://www.example.com)
```

### *Creating tables* 
Quarto makes it easy to include tables in your documents:

1. **Insert Table**: To add a table, select the location in your document where you want the table to appear.
2. **Specify Rows and Columns**: Define the number of rows and columns you need for your table.

Example:
```markdown
| Header 1 | Header 2 |
|----------|----------|
| Data 1   | Data 2   |
| Data 3   | Data 4   |
```

### *Adding Formulas*
For mathematical content, you can incorporate formulas into your Quarto documents using LaTeX syntax. LaTeX is a widely-used typesetting system for scientific documents.


```markdown
$\frac{n!}{k!(n-k)!} = \binom{n}{k}$
```


## 5 Code in Quarto Documents 

Quarto does things a bit differently than standard code writing. Instead of starting with code, you begin by adding text. But how does Quarto know what's code and what's not, without using comments like #?

That's where **"Code Chunks"** come in handy. Think of them as the bridge between your words and the code's magic. Here's how it all works:

### What is Knitr? 

Knitr is a special tool inside RStudio that powers the dynamic part of Quarto reports. It allows you to smoothly mix R code into your Quarto documents, whether they end up as HTML, Word, PDF, or LaTeX files. Knitr is essential for a concept called **Literate Programming**, which helps make your work reproducible.

### Writing Code with Code Chunks 📝

#### Adding a Code Chunk

You have a few ways to insert a code chunk into your Quarto document:

- Use the **Insert > Code Chunk** option in the editor's toolbar.
- Manually type the code chunk's special markers: `{r}` and triple backticks (\```).
  *If you're in "editor" mode, remember to close the code chunk with triple backticks as well (\```).*
- Or just press the keyboard shortcut: Ctrl + Alt + I (Windows) or Cmd + Option + I (Mac).

📷 [Include a figure or screenshot showing how to add an R code chunk here]

Here are some common settings for code chunks:

- **include**: A yes/no choice to put the chunk's result in your document (it's usually yes).
- **eval**: A yes/no choice to run the code or not (yes is common), or you can specify which lines to run.
- **echo**: A yes/no choice to display the code (often yes).
- **results**: A yes/no choice to show the code's results in your document (yes is typical).
- **warning**: A yes/no choice to display warnings (often yes).
- **message**: A yes/no choice to show messages when running the code (often yes).

#### Label Your Code Chunk

Before we make our code look pretty when it runs, let's give it a name. This step isn't required for running code, but it helps if you want to do fancy things with your Qmd files later, like cross-referencing.

Here's what you need to know:

- The label format is simple: `#| label: chunk-label`.
- Each chunk must have a unique label.


### Bibliography 

# Lets build together a QUarto paper/Document 

Maybe we should do this as exercise format 

## 1. Download needed data for the current examples of literate programming document 
data

## 2. Upload needed packages  
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

## 4.6 Lets work on the Quarto file 
Hopefully, by now you have Quarto downloaded in your R 

### 4.6.0 Make changes to the YAML 

``` yaml
---
title: "Example analysis breast cancer data"
author: "Name of the researcher or team"
bibliography: references.bib
date: "`r Sys.Date()`"
toc: true
number-sections: true
highlight-style: pygments
execute:
  echo: false
format:
  gfm: default
  html:
    code-fold: true
    code-tools: true
    df-print: paged
editor: visual
---
```
### 4.6.1 Put in some text 
Introduction to the data used and try to link to available resources 

## Introduction
This is an example analysis of the **Wisconsin breast cancer data** (available [here](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)) done in R. The first usage of this data was described in @Streetetal1993.


### Additional resources 




