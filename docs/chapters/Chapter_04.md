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

1. **Code Execution**: Your Quarto document (`.qmd`) is first processed by ![**knitr**](https://yihui.org/knitr/), which executes the code chunks embedded within the document, producing an intermediate Markdown (`.md`) file that includes both the original code and its output.
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
# ----read-data----
cancer_data <- read.csv("data/breast-cancer-wisconsin.csv")
head(cancer_data)
cancer_data$diagnosis <- as.factor(cancer_data$diagnosis)
```

### 4.5.3 Creating Your First Quarto Document

![Screenshot of my chart](https://github.com/elixir-europe-training/ELIXIR-TrP-LiterateProgrammingR-CodeRep/blob/main/docs/chapters/Figure1.png)

*Figure A: An example of a Quarto document in RStudio, showcasing integrated code and results.*

To start creating your own Quarto document in RStudio:
1. Go to **File > New File > Quarto Document...**.
2. Follow the prompts in the wizard to configure your document, choosing from a variety of templates and settings to suit your project's needs.

#### 4.5.3.1 YAML Header (Metadata)

The **YAML metadata** in a Quarto document is crucial for defining the document's metadata, which influences its rendering. This metadata includes details like the document's title, author, desired output format, and other rendering options. It's encapsulated by three dashes (`--- `) at the top of the document.

Example YAML Header:

```{yamal}
---
title: "Insightful Analysis"
author: "Jane Doe"
execute:
  echo: false
format: html
---
```

This header sets up the document with a title, an author, specifies that code echoes should be suppressed (echo: false), and designates HTML as the output format.


### 4.5.4 Rendering a Qmd Document

**Rendering** a `.qmd` (Quarto Markdown) document transforms it into a different format like HTML, PDF, or Word. This process compiles your code and applies settings from the document's YAML header. Before rendering, ensure your document is error-free.

**Steps to Render Your Document:**

1. **Save Your Document**: Name it `my_first_qmd.qmd` and save it in an accessible location.

2. **Render**: Locate and click the **"Render"** button in your Quarto editor. This button is often found at the top or bottom of the editor interface.

**FIGURE:** ![Insert a screenshot of the "Render" button here.]

<details>
<summary><strong>📝 Exercise: Produce your own Quarto document</strong></summary>
<p>

1. Create a new Quarto document in your editor (e.g., RStudio).
2. Add a title and your name as the author in the YAML header.
3. Set the output format to HTML.
4. Render the document.

</p>
</details>

<details>
<summary><strong>✅ Solution:</strong></summary>
<p>

1. **Create Document**: In RStudio, use `File > New File > Quarto Document`.
2. **Edit YAML Header**: Add `title: "Your Title"` and `author: "Your Name"`.
3. **Set Output**: Ensure the YAML includes `format: html`.
4. **Render**: Click the "Render" button to produce your HTML document.

*Insert screenshots demonstrating each step for clarity.*

</p>
</details>


*Insert screenshots demonstrating each step for clarity.*

        To do : *[Provide screenshots of the solution here]* or describe it 
        
## 4.5 Writing Quarto Documents

### RStudio Visual Editor: Simplified Formatting

The RStudio Visual Editor offers a user-friendly approach to formatting Quarto documents, featuring a rich text interface similar to popular word processors. This guide will help you navigate the essential features of the Visual Editor to enhance your document creation process.

#### Activate Visual Mode

To access the Visual Editor, click the "Visual" option at the top-left corner of the toolbar. This action activates a formatting toolbar reminiscent of Google Docs, providing intuitive access to formatting options.

#### Switch Between Modes

RStudio allows you to toggle between Source and Visual modes effortlessly, enabling you to work with the code directly or through the visual interface without losing your place. This flexibility ensures that you can enjoy the best of both worlds—direct code manipulation and simplified visual editing.

### Writing Text

#### Adding Headings

Headings structure your document and guide your readers through sections. In the Visual Editor, headings can be added directly or through Markdown syntax.

For keyboard shortcuts to add headings and other formatting, refer to the RStudio editing shortcuts (add link).

_Example:_

```markdown
# Heading 1
This is a sentence with some **bold text**, some *italic text*, and an ![image](image.png).
```

### Creating Bullet and Numbered Lists

Lists are essential for organizing information in a readable format. Quarto supports both bullet and numbered lists, allowing you to structure your content effectively.

#### Bullet Lists

To create a bullet list, start each item with a `-`, `*`, or `+`, followed by a space. This simple syntax transforms plain text into an organized list.

_Example:_

```markdown
- Item 1
- Item 2
  - Subitem 2.1
  - Subitem 2.2
- Item 3
```

### Numbered Lists

For sequences or steps, numbered lists are the go-to. Begin each line with a number, followed by a period and a space. Quarto automatically takes care of the numbering for you, ensuring your list is orderly and sequential.

```markdown
1. First step
2. Second step
   1. Substep a
   2. Substep b
3. Third step
```
### Adding Images

Images significantly enhance the visual appeal and clarity of documents. To insert an image in Quarto, use the following syntax:

```markdown
![Alt text for the image](path/to/image.png "Optional title")
```

### *Adding Images*
You can enhance your Quarto documents by adding images. The visual editor simplifies this process:

**Browse and Insert**: Click on the image icon in the formatting bar, browse your computer to find the image file, and insert it into your Qmd document.
Example
```
![Alt Text](image.png)
```
This markup instructs Quarto to display an image located at `path/to/image.png`, with "Alt text for the image" serving as alternative text for accessibility purposes, and an "Optional title" that appears when hovering over the image.

### Adding Links

Links are essential for directing your readers to external references or for providing further reading materials. Adding links in Quarto is straightforward with the following Markdown syntax:

```markdown
[Link text here](https://www.example.com "Optional title")
```

The text within square brackets `[ ]` is what your readers will see as clickable text, and the URL within parentheses `( )` is where the link will take them upon clicking. An "Optional title" can also be included within quotes after the URL, which will appear as a tooltip during a mouse hover over the link.

### Creating Tables

Tables efficiently organize and present data and information in a structured format. In Quarto, you can create tables using Markdown's straightforward syntax:

```markdown
| Header 1 | Header 2 | Header 3 |
|----------|----------|----------|
| Row 1 Col 1 | Row 1 Col 2 | Row 1 Col 3 |
| Row 2 Col 1 | Row 2 Col 2 | Row 2 Col 3 |
| Row 3 Col 1 | Row 3 Col 2 | Row 3 Col 3 |

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







