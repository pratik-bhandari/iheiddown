# iheiddown <img src="graphics/iheidmytex.png" align="right" width="150"/>


This GitHub repository provides an R Markdown template for writing a PhD Dissertation at the Graduate Institute of International and Development Studies in Geneva based on the [IHEID  LaTeX dissertation template](https://github.com/jhollway/iheidmytex) and the R Bookdown package.

This project was inspired by by the [oxforddown](https://github.com/ulyngs/oxforddown),[thesisdown](https://github.com/ismayc/thesisdown), [huskydown](https://github.com/benmarwick/huskydown) and [bookdown](https://github.com/rstudio/bookdown) packages. If you are new to working with `bookdown` and `rmarkdown`, please read over the great documentation provided by `thesisdown`, `oxforddown` and in the [bookdown book](https://bookdown.org/yihui/bookdown/).


## Getting started

- LaTeX - download and install the MacTeX distribution from [tug.org/mactex/](http://www.tug.org/mactex/) (please be aware that it's quite large - 4.1 gigs!)
  - (For unclear reasons, Yihui Xie's [TinyTeX](https://yihui.name/tinytex/) is causing trouble! If you are normally using TinyTex for PDF output and can't get `iheiddown` to work, try uninstalling tinytex::uninstall_tinytex(), then install the MacTeX LaTeX distribution and restart RStudio.)
- [R](https://cran.rstudio.com) and [RStudio version 1.2 or higher](https://www.rstudio.com/products/rstudio/download/#download)
- The R packages `bookdown`, `tidyverse`, and `reticulate` (the other packages you need should be automatically installed when you build this project for the first time in RStudio)
- (If on a Mac): Command line developer tools. You can install these by typing `xcode-select --install` in a terminal prompt


## Writing your thesis

To use this template to write your thesis, do the following:
- update the YAML header (the stuff at the top between '---') in **index.Rmd** with your name, college, etc.
- write the individual chapters as **.Rmd** files in the root folder - **the introduction chapter *must* be named _00-introduction.Rmd**.
- write the front matter (abstract, acknowledgements, abbreviations) and back matter (appendices) by adjusting the **.Rmd** files in the **front-and-back-matter/** folder
- for abbreviations, change **front-and-back-matter/abbreviations.tex** to fit your needs (follow the LaTeX syntax in there)

**.Rmd** files you don't want included in the body text must be given file names that begin with an underscore (e.g. **front-and-back-matter/\_abstract.Rmd** and **front-and-back-matter/\_acknowledgements.Rmd**). (Alternatively, specify manually in **\_bookdown.yml** which files should be merged into the body text.)


## Knitting individual chapters

To knit an individual chapter without compiling the entire thesis:
1. open the **.Rmd** file of a chapter
2. add a YAML header specifying the output format(s) (e.g. `bookdown::word_document2` for a word document you might want to upload to Google Docs for feedback from collaborators)
3. Click the `knit` button (the output file is then saved in the root folder)

As shown in the sample chapters' YAML headers, to output a single chapter to PDF, use:

```yaml
output:
  bookdown::pdf_document2:
    template: templates/iheiddiss.tex
```
This will format the chapter in the myiheidtex style but without including the front matter (table of contents, abstract, etc)

## Output 

The PDF version is fully functional. The word, gitbook and epub versions might be developed at a later time.


## Feedback

Please get in touch with [me](https://jameshollway.com) or raise an issue for this repo
if you encounter any bugs, if you have any suggestions, or if you want to contribute.
