## 1.1 What is Literate programming?
The expression "Literate programming" was coined in 1984 by the Mathematician and Computer Scientist [Donald Knuth](https://en.wikipedia.org/wiki/Donald_Knuth). It involves an explanation of how a program works in a natural language as opposed to the syntax of a formal programming language (Like R & Python).   

## 1.2 Why do we need Literate programming?
Have you ever considered how a computer "reads' its instructions? At the silicon level ([Machine code](https://en.wikipedia.org/wiki/Machine_code)) the language is purely binary numbers i.e. 1s and 0s and comprise of extremely mechanistic operations e.g. roll bits to left. This is not very intuitive to humans so when we write computer programs we tend to write them in high-level languages like R & Python which are a very structured, very natural form of English.    
They are written to be read and understood by __Humans__. In fact, other programs (interpreters and compilers are necessary for the computer to actually make sense of our code. Since this form of the code is clearly designed to be read by humans, it is emminently sensible to make the logical goals of the program equally readasble by humans.    

Like any other form of scientific communication (Papers, Posters or Lectures) an anlysis script or program is a narration of a scientific story.
Use of Literate programming enbles us to annotate the programs code with meaningful insights into the assumptions, considerations and decisions involved in the analyssis of the data. Which in turn leades to more unerstandable and reproducible research.       

## 1.3 How can we implement Literate programming?
We could choose to annotate our code in many ways. Programming languages both feature and encourage the use of comments in coding. Whilst these are adequate for discussing the program in terms of the feature-set of the programming language, they are lacking in the ability to provide rich formatted dialogue with emphasus styles such as bold and italics or to incorporate images and diagrams. Similarly, the code and it's outputs remain distinct and seperate entities.    

So what would help us is a language that can have the code and its outputs embedded in our exposition of the analysis. This should be written in a form aimed at humans not computers and spporting rich formatting similar to a word-processed document.   

* In this course, one of the key deliverables is for you to gain familiarity with a language called Markdown. This is a very simple language that enables you to code formatted text using a simple [ASCII](https://en.wikipedia.org/wiki/ASCII) text editor and in appropriate Integrated Design Environments (IDEs) like PyCharm, Quarto,Jupyter Notebooks and Rstudio allow you to intersperse foramtted text blocks with computer code chunks and practically implement the concept of literate programming.    
* Another deliverable of this course will be to also provide an introduction to at least one of these IDEs and how they support you in carrying out literate programming.   
* There will be a practical implementation of literate programming where we will transform a plain script into an annotated, rich markdown implementation that retains the functionality of the computational workflow but additionally narrates the concepts of said workflow.   
<hr>
## 99.1 Introduction to Markdown
Here you can enter text and create inline citations[@Garcia2020] by using the bibtex plugin. Add your references in `references.bib`, and cite [@hoebelheinrich_nancy_j_2022_6769695] by adding the @refid inside brackets like this `[@10.1093/bioinformatics/btt113]`

You can also embed videos from a local source (with a relative path) or from an url (like youtube). To use a youtube URL, 
just attach the ID of the video to a youtube embedded video link: `https://youtube.com/embed/`. For example, the Elixir training video `https://youtu.be/oAD8FdGf8tI` has the ID `oAD8FdGf8tI`, so the final link would be:

```
![type:video](https://youtube.com/embed/oAD8FdGf8tI)
```

![type:video](https://youtube.com/embed/oAD8FdGf8tI)

## 99.2 Second subtopic

!!! note "Note"

    Here you can put a note using admonitions.

    Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur. Excepteur sint occaecat cupidatat non proident, sunt in culpa qui officia deserunt mollit anim id est laborum.

## 99.3 Third subtopic


