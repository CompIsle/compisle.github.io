# Rendering Markdown as PDF within Visual Studio Code

## Intro

There is more than one way to do this. The most flexible, which would give you the ability to convert Markdown into a bewildering number of formats including docx, is to install pandoc. If youe are interested, Dave Johnson covers it in detail in a [blog](https://thisdavej.com/build-an-amazing-markdown-editor-using-visual-studio-code-and-pandoc/).
If _all_ we want is to output Markdown as PDFs (and incidentally HTML) then there is an easier way, use Jebbs' marvellous __Markdown Extended__ extension for Visual Studio Code.

### Install the extension

If you are not sure how to add an extension to Visual Studio Code - then you probably aren't ready for this, but there is a [video](https://code.visualstudio.com/docs/introvideos/extend) covering the process on the code website.

So, we'll assume the extension is installed.

## Usage

Markdown Extended vastly increases Visual Studio Code's markdown handling capabilities (which are already probably more extensive than you imagined, [this article](https://code.visualstudio.com/Docs/languages/markdown) on the code website is well worth reading).

To begin with it (rather obviously) adds support for Extended Markdown - see [syntax guide](https://www.markdownguide.org/extended-syntax/) which gives better support for tables and code blocks, footnotes, strikethrough, task lists ....

All of these extended features can be disabled on a granular basis via the configuration file.

It also provides an exporter which is capable of turning Markdown into PDF. To achieve this it uses a headless version of Chrome and the first time you try this it will need to be installed - so give permission when asked.

It is then as easy as right-clicking somehere in your `.md` editor window, and selecting `Export to File`. The familiar VSC command dropdown will appear and you choose `PDF file`. After a few moments - depending on how complex your document is - a file with a `.pdf` extension will be created, alongside your original file (unless you have changed the default output folder in the extension's settings).

This will only work entirely as expected if your Markdown is correct - so either use a linter (the markdownlint extension of David Anson works well although you may want to turn off warnings MD007 and MD036 with Extended Markdown) or examine VSC's preview carefully (`Ctrl-Shift-V` opens the preview pane if clicking on icons is not your thing).

I would also save the file before converting to PDF although the exporter does cope with unsaved changes.

### Why PDF?

Markdown is a fine format until  

+ You want to use images, and ...
+ Move the file

Because then any local image links will break. So, for instance, if you have included screenshots there is a problem unless you have access to a CDN ...

Also Markdown is potentially problematic if sharing with people who may not have a Markdown previewer.

Both of these considerations apply with work for assessment.

Converting your file into PDF has the effect of embedding the images in the document, so it becomes completely self-contained. As a bonus, it is also immutable.

### A quick guide to using images

I usually proceed much as I do with HTML. Wherever I am editing my Markdown I have an `img` subfolder in which I put any images.

Within my Markdown I can then add markup like this

```markdown
![alt text](./img/imageone.png)
```

or even better, using references rather than in-line urls (easier to maintain)

```markdown
![alt text][image1]
...
[image1]: ./img/imageone.png
```

### A note on styling

The documents referenced back at the beginning would lead you to this but the `TL;DR` version is

include an array of any stylesheets you want to use for markdown in your user or workspace settings

```json
"markdown.styles": [
	"https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css",
	"./css/mystyles.css"
]
```

### Other useful Markdown Extensions

`Markdown Math` if you want full KaTeX support for mathematics and equations.
`Markdown Preview Mermaid Support` if you need flow charts, state diagrams
