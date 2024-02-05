## 4.1 What's Our Goal? 🎯

Welcome to Quarto!

By the end of this chapter, you'll have a solid understanding of Quarto and how to use it to create reproducible, visually appealing scientific reports, presentations, and publications.

## 4.2 What is Quarto, and Why Does It Matter? 📖
Quarto (link quarto) is not just an evolution of R Markdown; it's a tool designed by Posit to meet the demands of data scientists, researchers, and educators. This open-source publishing system, powered by Pandoc, transcends traditional barriers by supporting multiple programming languages like R, Python, and Julia, and offering a variety of output formats including HTML, PDF, MS Word, and ePub.

**Key benefits of Quarto:**
- Multi-language support: Facilitates seamless integration of R, Python, Julia, and Observable JS, catering to interdisciplinary projects.
- Versatility in Output Formats: From academic PDFs to web pages and presentations, Quarto adapts your work for any audience.
- Guaranteed Reproducibility: Ensures your research can be easily verified, fostering a culture of transparency and reliability.

In addition, it enables users to:
- Design personal or project websites
- Craft tutorials, textbooks, and other online educational resources

Explore the [Quarto gallery](https://quarto.org/docs/gallery/) to see its capabilities. 

## 4.3 Before We Begin 🛠️
In this part of the tutorial, we'll focus on using Quarto with R. But remember, Quarto isn't limited to [R](https://quarto.org/docs/computations/r.html) — it also works with Python, Julia, and Observable JS!

### 4.4.0 Installation Guide ⚙️
Before we start, it's essential to set up our environment. Here's what you need:

1. **RStudio Installation**: Ensure you have the latest version of RStudio. This will provide the best compatibility with Quarto.

2. **Quarto Installation:** Visit the [Quarto website](https://quarto.org/) for installation instructions. For a more detailed guide, check out the [Quarto guide]([https://quarto.org/](https://quarto.org/docs/guide/)). Make sure to follow the steps appropriate for your operating system.
   
3. **TinyTeX Setup**
TinyTeX is a minimal TeX distribution specifically tailored for Quarto, which you'll need for generating PDFs. Here's how to install it:
- Open RStudio, navigate to *Tools* > *Terminal* > *New Terminal*.
- In the terminal, type *quarto install tinytex* to start the installation process.

4. **Update R Packages**
To ensure smooth operation with Quarto, update the following R packages by running this command in RStudio:

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

## 4.4 Let's Dive In! 🌊

### 4.5.1 The Quarto Workflow
Quarto simplifies document creation through a two-step process:

1. **Code Execution**: Your Quarto document (`.qmd`) is first processed by ![**knitr**](https://yihui.org/knitr/), which executes the code chunks embedded within the document, producing an intermediate Markdown (.md) file that includes both the original code and its output.
2. **Final Rendering**:  The Markdown file is then handed over to ![**pandoc**](https://pandoc.org), which converts it into the final document in the desired output format. This process is highly flexible, supporting a wide array of formats including HTML, PDF, and Word documents.

*[Include a visual diagram of the Quarto workflow here]*

### 4.5.2 Understanding the Quarto Document
Quarto documents bring together code, results, and narrative in a single file, enhancing reproducibility and clarity. Here are the key components:

1. **The YAML Header**: At the start of your document, the YAML header specifies important settings for document rendering, such as title, author, output formats, and more. This metadata is crucial for controlling the appearance and behavior of your final document.
2. **Quarto-formatted Text**: Narrative text follows Markdown syntax, allowing for straightforward formatting of headers, lists, links, and more. This makes your document both readable and versatile.
3. **R Code Chunks**: Enclosed by three backticks (```), code chunks can contain R code (or other supported languages) for executing within your document. These chunks can perform data analysis, visualize results, and more. You can directly copy and paste existing R scripts into these chunks, with Quarto handling the execution and integration of results into the final document.

Quarto's flexibility extends to supporting multiple programming languages within the same document, facilitating interdisciplinary collaboration and analysis.

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

!!! question "Excercise"
       
       Let's produce your own document 
       1. Use **RStudio** to create a new default Quarto document.
       1. Add a **title** to your document
       2. Specify your **name as the author**.
       3. Change the **format** to **HTML**
       4. **render the document**.

    ??? success "Solution"

        To do : *[Provide screenshots of the solution here]* or describe it 
        
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


# Let's Build a Quarto Paper/Document

Before we start, ensure you have downloaded [the data]([https://www.example.com](https://www.kaggle.com/datasets/uciml/breast-cancer-wisconsin-data)).

## Step 0: Create a YAML Header
Before we dive into the document's content, let's set up the YAML front matter for your document titled "Breast Cancer Data Analysis." Follow these instructions:

1. Set the title of the document to "Breast Cancer Data Analysis."
2. Specify the author as your research team's name.
3. Use the bibliography file named "references.bib."
4. Ensure that the document includes the current date.
5. Enable a table of contents for the document.
6. Number the sections in the document.
7. Choose the Pygments highlight style for code.
8. Hide code echo during code execution.
9. For HTML output, enable code folding, code tools, and paged data frame printing.
10. Specify a preference for a visual editor.

Fill in the missing information and structure the YAML front matter according to the provided instructions. Once completed, you'll have a properly configured YAML header for your document, suitable for analysis and presentation.

<details>
<summary><strong>Solution: YAML Header</strong></summary>

```yaml
---
title: "Breast Cancer Data Analysis"
author: "Your Research Team's Name"
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

**Figure 2**: how the Quarto HTML document head looks
![Screenshot of my chart](https://github.com/elixir-europe-training/ELIXIR-TrP-LiterateProgrammingR-CodeRep/blob/main/docs/chapters/Figure_CodRep/CodeRep1.png)
</details>

## Step 1: Import Required Packages
In this step, create a code chunk that imports the necessary packages: `tibble`, `dplyr`, `readr`, `ggplot2`, `caret`, `ROCR`, and `pROC`.

<details>
<summary><strong>Solution: Import Required Packages (Step 1)</strong></summary>

```R
# Load the required packages
# Make sure to install them first if you haven't already
library(tibble)   # Provides a modern, tidy alternative to data frames.
library(dplyr)    # Data manipulation.
library(readr)    # Reading CSV file data.
library(ggplot2)  # Plotting system.
library(caret)    # Machine learning.
library(ROCR)     # Evaluating and visualizing the performance of binary classifiers.
library(pROC)     # Evaluating and visualizing the performance of binary and multi-class classifiers using ROC analysis.
theme_set(theme_bw(12))
knitr::opts_chunk$set(fig.align = "center")

```
**Figure 3**: how the Quarto HTML importing document looks
![Screenshot of my chart](https://github.com/elixir-europe-training/ELIXIR-TrP-LiterateProgrammingR-CodeRep/blob/main/docs/chapters/Figure_CodRep/CoderRep2.png)
</details>

## Step 2: Insert text and code 
Objective: Integrate the provided text and code into your Quarto document.

Instructions:

1. Incorporate the given text and code snippets into the body of your Quarto document.
2. As you insert key points or emphasize specific terms, utilize Bold, Italic, or any other relevant styles to enhance readability and highlight importance.


**Text**: "Now we read the data, available as a local csv file in the relative path (`breast-cancer-wisconsin/`) below. We use various functions to have a glimpse of its structure and dimensions. We also change the `diagnosis` variable to a factor."

**Code**: 
cancer_data <- as_tibble(read.csv("data/breast-cancer-wisconsin.csv"))
head(cancer_data)
cancer_data$diagnosis <- as.factor(cancer_data$diagnosis)
colnames(cancer_data)
dim(cancer_data)

**Text**
"Echoing the dimensions printed in the output above, this data frame has `r nrow(cancer_data)` rows and `r ncol(cancer_data)` columns. Except for the first two columns, the remaining columns are features computed from a digitized image of a fine needle aspirate (FNA) of a breast mass. They describe characteristics of the cell nuclei present in the image."

We use the following code to remove columns with missing values (`NA`), and have a glimpse of the remaining columns again.

**Code**
cancer_data <- cancer_data |> select(where(~ all(!is.na(.x))))
head(cancer_data)

<details>
<summary><strong>Solution: Insert text and code (Step 2)</strong></summary>

Now we read the data, available as a local csv file in the relative path (`breast-cancer-wisconsin/`) below. We use various functions to have a glimpse of its structure and dimensions. We also change the `diagnosis` variable to a factor.

```{r read}
cancer_data <- as_tibble(read.csv("data/breast-cancer-wisconsin.csv"))
head(cancer_data)
cancer_data$diagnosis <- as.factor(cancer_data$diagnosis)
colnames(cancer_data)
dim(cancer_data)
```
Echoing the dimensions printed in the output above, this data frame has `r nrow(cancer_data)` rows and `r ncol(cancer_data)` columns. Except for the first two columns, the remaining columns are features computed from a digitized image of a fine needle aspirate (FNA) of a breast mass. They describe the characteristics of the cell nuclei present in the image.

We use the following code to remove columns with missing values (`NA`), and have a glimpse of the remaining columns again.
```{r remove_na}
cancer_data <- cancer_data |> select(where(~ all(!is.na(.x))))
head(cancer_data)
```
</details>

ADD SCREENSHOT ON HOW IT LOOK 


## Step 3: Visualizations in Quarto documents 
TEXT OF THE EXCERCISE

<details>
<summary><strong>Solution: Insert text and code (Step 2)</strong></summary>
  
## Basic summaries
Using the column `diagnosis` in the data, we count that there are `r sum(cancer_data$diagnosis == "M")` Malignant tumours and `r sum(cancer_data$diagnosis == "B")` Benign tumours. We can also plot these counts:
```{r plot-counts, fig.cap = "Counts of data according to tumour status", fig.align = "center", out.width = "70%", fig.asp = 0.65, message = FALSE}
plot_count(cancer_data)
```

# Visualisations and tests of three features
To understand the data better, it is useful to look at, for each tumour status, the distribution of individual features / variables. As an illustration, we shall look at three of them.

## Histogram & density
We first visualise such distributions using histograms and density plots in Figure \@ref(fig:plot-hist). As the same kind of plot is required, a function is written for convenience.

```{r plot-hist, fig.show = "hold", fig.cap = "Histogram and density of three features according to tumour status", fig.align = "center", out.width = "70%", fig.asp = 0.65, message = FALSE}
plot_hist_den(
  cancer_data, var = area_worst, label = "Area worst", filename = "hist_area.png"
)
plot_hist_den(
  cancer_data, var = fractal_dimension_mean, label = "Fractal dimension mean",
  filename = "hist_frac.png"
)
plot_hist_den(
  cancer_data, var = radius_se, label = "Radius se", filename = "hist_radius.png"
)
```

## Boxplots
Another way of visualising the distribution of the three variables above, grouped by the tumuor status, is the box plots in Figure \@ref(fig:plot-boxplot):

```{r plot-boxplot, fig.cap = "Boxplot of three features according to tumour status", fig.show = "hold", fig.pos = "!h", fig.align = "center", out.width = "70%", fig.asp = 0.65, message = FALSE}
plot_boxplot(
  cancer_data, var = area_worst, label = "Area worst", filename = "boxplot_area.png"
)
plot_boxplot(
  cancer_data, var = fractal_dimension_mean, label = "Fractal dimension mean",
  filename = "boxplot_frac.png"
)
plot_boxplot(
  cancer_data, var = radius_se, label = "Radius se", filename = "boxplot_radius.png"
)
```
</details>

## Step 4: Reporting tables 

<details>
<summary><strong>Solution: Insert text and code (Step 2)</strong></summary>

Statistical tests

We can perform two-sample *t*-test to find out if there is a significant difference in the distribution of a feature according to the tumour status.
```{r ttest, results = "hold"}
area_worst_B <- cancer_data$area_worst[cancer_data$diagnosis == "B"]
area_worst_M <- cancer_data$area_worst[cancer_data$diagnosis == "M"]
ttest0 <- t.test(area_worst_B, area_worst_M, var.equal = TRUE)
options(scipen = 3, digits = 3)
```

The $t$-statistic is `r ttest0$statistic` and the $p$-value is `r ttest0$p.value`. We can write a function to carry out the test more systematically:
```{r ttest_functional}
ttest1 <- ttest_var(cancer_data, var = area_worst)
ttest2 <- ttest_var(cancer_data, var = fractal_dimension_mean)
ttest3 <- ttest_var(cancer_data, var = radius_se)
```

The results are in the following table:

| Variable | $t$-statistic | $p$-value |
|----------|---------------|-----------|
|Area worst|`r ttest1$statistic`| `r ttest1$p.value`|
|Fractal dimension mean|`r ttest2$statistic`| `r ttest2$p.value`|
|Radius se|`r ttest3$statistic`| `r ttest3$p.value`|
</details>







