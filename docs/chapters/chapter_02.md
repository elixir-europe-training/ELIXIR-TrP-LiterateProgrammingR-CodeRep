## Introduction
This chapter is a gentle introduction to the literate programming approach, and a preview of the components that will be covered in the next few chapters. By the end of this chapter, it is hoped that you will find this approach useful and understand its basics.

## Workflow
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
However, chances are that the analysis changes direction as you go along, and/or that the data is updated. So you re-run the scripts, save the image files, (optionally) upload them, and generate the deliverable again. And this is usually done multiple times and in an iterative fashion. One or more of the following scenarios may eventually happen:
1. You have changed the analysis and edited the programming scripts on your computer, but haven't updated the results (plots, numbers, tables) in the plain text files. When you revisit the deliverable after some time, the results reported do not match what you get from running the scripts.
2. You have decided to change the analysis to a previous direction, but because the scripts have been updated, you cannot revert exactly to what you want.
3. To avoid the above scenario, you create a new set of programming scripts every time you change the analysis. Eventually it becomes difficult to find the right version (again).

I hope you feel dissatisfied with this workflow, because then you will benefit from this training programme!

## I wish there's a way of putting them together
There is!

### Plain script vs a literate programming script

## I'm confused with all these terms
Don't worry, we've got you covered

- RStudio: primarily Integrated Development Environment (IDE) for R, but growing support for other languages (Julia, Python)
- Markdown: as a testament, these materials are written in Markdown
- Rmarkdown: essentially R + Markdown, generating results dynamically, thus guaranteeing reproducibility
- YAML: the definition is not very useful; essentially a preamble; similar to lines before `\begin{document}` in a .tex file
- Quarto: the next version of Rmarkdown i.e. R/Python/Julia etc. + Markdown

