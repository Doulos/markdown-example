# About this folder

This folder contains examples of Markdown text including this document, `README.md` that you are reading right now [^1]. If you open this file with a *plain text editor* such as Notepad++ (Windows), TextEdit (Mac) or Vim (Linux), you will see the raw Markdown syntax. It is quite readable with the plain approach; however, you can also view it in a Markdown editor such as the Typora application. Typora allows you to edit Markdown in an intuitive manner such as you might edit a document in Word.

The `Example.md` file provides a richer example of the things that Markdown can do, and Typora can export (i.e., Save As...) the rendered text in any of many different formats including EPUB, HTML, PDF, RTF or Word.

Open the example to explore. You will also notice an assets folder. It contains images. Typora allows you to drag and drop image files into the Markdown.

You can also use [Pandoc](https://pandoc.org/index.html) And [Mermaid](https://mermaid.js.org/) to directly convert if you install [pandoc](https://pandoc.org/installing.html) and the [mermaid-filter](https://github.com/raghur/mermaid-filter). Here is mythe command to create html for example:

```bash
pandoc --metadata pagetitle="Markdown Example" --self-contained --css=style.css -F mermaid-filter --mathjax -f gfm -t html -o Alternate.html Example.md
```

[^1]: Footnote: You might also be viewing the HTML, PDF or Word versions of this file that were exported using Typora.

Note: I have exported **this** document using a custom "Typora theme", which is really just the selection of a set of CSS styles. Typora allows users to provide custom themes. Hence we can have a Doulos theme. d
