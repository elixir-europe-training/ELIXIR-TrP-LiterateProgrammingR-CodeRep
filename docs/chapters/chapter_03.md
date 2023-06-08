## 3.1 What is Markdown?

Markdown is a simple markup language created by [John Gruber in 2004](https://daringfireball.net/projects/markdown/). As a markup language, Markdown, allows you to format plain text to enhance presentation and readability of your text.  From a technical perspective, Markdown is two things: (i) a syntax or grammar for formatting plain text files and; (2) a software tool that converts plain text files to HTML. As a software Markdown is free and platform independent, meaning it can br run any device using any operating system.

When using Markdown you annotate your text with chracters, such  as\*s or \#s, to achieve a desired formatting effect on that text (e.g. make a heading). In this sense it is different from [WYSIWYG](https://en.wikipedia.org/wiki/WYSIWYG) editors like Microsoft Word where you use buttons, keystrokes and mouse strokes to acheive a desired effect. Also, unlike WYSIWYG editors, you won't see the fruit of your formatting labours without an additional step of rendering your plain text file or notebook document into an HTML or other document format (these days some IDE's, e.g. the [visual markdown editor in RStudio](https://posit.co/blog/exploring-rstudio-visual-markdown-editor/), support WYSIWYG rendering of Markdown in real time). 


## 3.2 Why Markdown for Literate Programming?

Recall that for literate programming, the narrative, rather than code, is the key focus, hence relevant and appropriate formatting of your text (e.g. using **bold** or *italic* font or incorporating images) is essential for other humans (perhaps your colleagues) to make sense of and engage with your code or analysis. Hence, literate programming involves mixing your code (written in Python,R etc.) with a document formatting or typesetting language to format your expositry narrative. HTML and [LaTeX](https://www.latex-project.org/) are two popular markup languages utilized for document formatting in literate programming for scientific research. However, unlike these other markup langguages, Markdown is simple and lightweight. This means you can focus on constructing engaging and efficient narrative without kicking a fuss over what code or tag is required to make your text appear, for e.g., in bold or italic font. Compared to other markup languages, you can learn Markdown quickly and hence focus more on your content writing.

**Figure 3.1** displays a comparison of the code require to format plain text into bold, italic or both in LaTex _versus_ Markdown. From the code below it showed be obvious how the markdown syntax is much simpler than LaTeX (or indeed other markup languages). Additionally, withouth even rendering the markdown annotated text, it remains easily readable by humans. More complex formatting like generating tables, inserting images, requires even more complex code in markup languages like LaTex or HTML, but remains simple in Markdown as you will see in the next section. This simplicity of Markdown means there is little overhead in learning the document formatting language for literate programming, freeing your mind to focus on your content.
 
<figure>
<img src="../../assets/images/LaTeXvsMd.png" width="100%"  alt="Image comparing LaTex vs. Markdown sytnax"/>
<figcaption> Figure 3.1 Comparing markup syntax of Latex verus Markdown. Code for either markup language is highlighted in yellow. On rendering either document, the markedup text should display in bold, italics or both. </figcaption>
</figure>

Markdown's growing popularity as the document formatting language of choice in literate programming needs is reflected in the availability of markdown support (in many cases right out of the box without any additional installation!) for popular IDEs and notebook formats such as RStudio, VS Code, Jupyter Notebooks (NEEDS FACT CHECKED) and even GitHub (a code hosting platform for colloboration and version control - if you are unfamiliar with GitHub, don't worry, this will be covered in the next module). However, Markdown's simplicity comes at a cost: there are only a limited amount of formatting effects available to you.  If your needs ever grow, worry not, tools like [pandoc](LINK) allows you to mix more flexible formatting languages such as LaTeX and/or HTML with Markdown allowing you to format your text to your heart's desire. However, For most narratives , the formatting elements in Markdown will be sufficient and our focus in this lesson (and on remainder of this course) will be on learning Markdown syntax. In the following chapters you can implement in your Markdown skills for literate programming.

## 3.3 How to use Markdown

It's time to get our hands dirty and start getting some practise in how to use Markdown to format our text. To be able to follow the lessons below, you are going to need a Markdown editor, where we can write the Markdown language in a document but then also render or preview the document so we can see if the desire formatting effect was achieved.

:simple-rstudio:
If **Rstudio** your go to tool, you can do this by:
1. Go to the *File* menu, select *New file*, theb select *Quarto Document...*, alternatively you also use the **new file button** to do the same, and this is what is done in the video below. This will open up a *dialog* box with several options. Leave everything as default but **uncheck** the `use visual markdown editor` option. Feel free to add a **Title** and **Author** in the relevant fields, then hit the **create** button.
2. This will open a new **Quarto Document** in RStudio's **source** editor (this where you normally write your R scripts). You can then add your text and markdown annotation in the **body** of the document. The **body** of the document referes to any space below the text between the `---` at the top. This latter section is called the YAML and controls how the document will look when rendered. You can just ignore the YAML for now, we'll talk more about this in the next lesson (LINK TO NEXT CHAPTER). Note that RStudio will automatically generate some standard text, code and markdown to give you flavour of this literate programming document works. *Optional:* delete everything in the body of the file making sure **not to delete** the YAML.
3. After adding your text and markdown annotation to the document hit the `render` button to generate an HTML document (default). If you haven't yet saved your document, RStudio will ask you save the document before rendering. Once saved, RStudio will generate an HTML docuement that shows your text but formatted according to any markdown code. The next time you make a cahnge to your Quarto Document and hit **render**, RStudio will automatically save the changes to your Quarto document before rendering. Note: since 2021 RStudio now has also has a [**visual** markdown editor]([ ](https://posit.co/blog/exploring-rstudio-visual-markdown-editor/) that renders your markdown formatting live as you type it in the Quarto document, however, I wouldn't recommend this for the exercises below. 

[![type:video](https://youtube.com/embed/oAX9DSPVxX0)

:simple-jupyter:
If you are using **JupyterNotebooks**, you can create markdown cells to write formatted text in markdown:
1. In your JupyterNotebook, select **Markdown** from the drop-down menu on the centre middle of the screen.
2. Write your text and add your markdown formatting as you please within this cell.
3. In Jupyter Notebooks, you will immediately see the markdown annotation **and** the resulting formatting on the screen. To see the formatting only, hit the `Run` button

[![type:video](https://youtube.com/embed/7IwWejXqKTQ)

Finally, to learn markdown, we don't necessarily need RStudio or JupyterNotebooks, we can also use a standalone Markdown editor. [**Dillinger**](https://dillinger.io/) is a popular web-based Markdown editor and is sufficient to follow the rest of this lesson. If you want to use [Dillinger](https://dillinger.io/), just head on over to the link and see the video below on how to use this editor. It is extremely simple to use, write your text and markdown in the **editor window** to the left of your screen and you will immediately see the results in the **preview window** on the right.

[![type:video](https://youtube.com/embed/V8TV-r-Lafo)

You can use any of the 3 options from above to follow the markdown lessons below.

### 3.3.1 Formatting text

### 3.3.2 Adding Headers/Section Titles

### 3.3.3 Making Lists

### 3.3.4 Adding Images

### 3.3.5 Making Tables

## 3.4 Further Learning and Resources for Markdown
