# Literate Programming (in R)

## Authors

[cards class_name="authors" rows = "1" cols="4"(./docs/assets/cards/author_cards.yaml)]

## Lesson overview

!!! overview ""
    :fontawesome-regular-bookmark: **Description**  
    A course to introduce the theory, advantages and implementation of Literate Programming practices for R users working in RStudio to enhance the students abilities to produce reproducible code.    
   
    </br>
    
    :fontawesome-solid-arrow-left: **Prerequisites**  
    To be able to follow this course, learners should have knowledge in:  
    &emsp;1. Basic programming skills in R    
    &emsp;2. A familiarity in using the RStudio Integrated Development Environment    
    
    </br>
    
    :fontawesome-solid-arrow-right: **Learning Outcomes:**  
    By the end of the course, learners will be able to:    
    &emsp;1. Have an understanding of the principles and goals of Literate Programming (LP)  
    &emsp;2. Practically implement LP in their R programs using Markdown in Quarto/Rstudio      
    
    </br>
    
    :fontawesome-solid-users: **Target Audience:** Researchers, undergraduate students, postgraduate students, etc...  
    </br>
    
    :fontawesome-solid-stairs: **Level:** Beginner to Intermediate  
    
    :fontawesome-solid-lock: **License:** [Creative Commons Attribution 4.0 International License](https://creativecommons.org/licenses/by/4.0/)  
    
    :fontawesome-solid-money-bill-1: **Funding:** This project has received funding from [name of funders].  

    [comment]: # (Property in Bioschema: description)
    [comment]: # (Property in Bioschema: coursePrequsites)
    [comment]: # (Property in Bioschema: teaches)
    [comment]: # (Property in Bioschema: audience)
    [comment]: # (Property in Bioschema: educationalLevel)
    [comment]: # (Property in Biochema: licence)
    [comment]: # (This is an example for CONVERGE)

#### Contributors

[cards class_name="contributors" cols="6"(./docs/assets/cards/contributor_cards.yaml)]
Greek Mythology icons made by [max.icons](https://www.flaticon.com/authors/maxicons) from [www.flaticon.com](www.flaticon.com)

---
## Citing this lesson

Please cite as:

  1. Enter your citation here.
  2. Geert van Geest, Elin Kronander, Jose Alejandro Romero Herrera, Nadja Žlender, & Alexia Cardona. (2023). The ELIXIR Training Lesson Template - Developing Training Together (v1.0.0-alpha). Zenodo. https://doi.org/10.5281/zenodo.7913092. 

---
## Setup

### Data setup
To run this lesson you need to download the data [here](https://github.com/elixir-europe-training/ELIXIR-TrP-LiterateProgrammingR-CodeRep/tree/main/docs/data/breast-cancer-wisconsin.csv); the GitHub repository at which the csv file is situated also contains the scripts that generate the page you are looking at. To ensure that the code in [Chapter 4](./chapters/Chapter_04) works, it is recommended that you put the downloaded csv file a (sub-)directory called `data/` on your machine; see the example structure in [Chapter 2](./chapters/chapter_02/#221-example-structure).

### Software setup
The following is consistent with the [installation guide](./chapters/Chapter_04/#installation-guide) in [Chapter 4](./chapters/Chapter_04). To run this lesson you need to install the following:  

  * R - follow the instructions [here](https://cran.r-project.org/). You will need R for everything that follows.  
  * RStudio - follow the instructions [here](https://posit.co/download/rstudio-desktop/). You will need RStudio (and R) for Chapters [2](./chapters/chapter_02) and [3](./chapters/chapter_03).   
  * Quarto - follow the instructions [here](https://quarto.org/docs/get-started/). You will need Quarto (and R and RStudio) for Chapters [4](./chapters/Chapter_04) and [5](./chapters/chapter_05).  
  * TinyTex (R package) - required if you want to use LaTeX and/or render PDFs. This is an R package, more info and installation instructions [here](https://yihui.org/tinytex/).


