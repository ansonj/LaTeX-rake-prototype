# LaTeX + rake prototype

## What is this?

A handful of `.tex` files, plus a `Rakefile`, so you can quickly get started writing a beautifully-typset and fully-cited paper.

### What is LaTeX?

Text and code go in, pretty document comes out.

[Read this Wikibook](https://en.wikibooks.org/wiki/LaTeX); it's everything you need to know. I don't go into tons of detail here because the Wikibook is so exhaustive.

### Why should I use LaTeX?

It's the 21st century; you shouldn't have to fuss with WYSIWYG editors to make sure that all your section headers are formatted the same way. LaTeX allows you to focus on the *content* of your documents and let the computer take care of the rest.

LaTeX also allows you to organize your document as a series of modular files (this repository is an example). This helps you focus on one part of your document as a time. All of the little text files are very VCS-friendly, too.

## Requirements

- Ruby, specifically `rake`
    - [RVM](http://rvm.io) is your friend. I bet it includes `rake`, but if not, [please let me know and] you can `gem install rake`.
- LaTeX, specifically `pdflatex`
    - There are some [browser-based options](https://en.wikibooks.org/wiki/LaTeX/Installation#Online_solutions) if you want to see what LaTeX is all about before installing.
    - Install everything you need from [TeX Live](http://tug.org/texlive/), or [MacTeX for OS X](https://www.tug.org/mactex/).

## Usage

1. Download a zip or clone.
1. Pick your config options in the `Rakefile`.
    1. Change the target page length to match your assignment if you want.
    1. Turn off auto-cleaning of intermediate files if you want.
1. Write your document.
    1. Update `header.tex` with your info.
    1. Create separate `.tex` files for each chunk of your document and put their names in `master.tex` under "Document content."
    1. Update `todo.tex` to keep track of your progress.
    1. Put your sources in `src.bib`. (I use [BibDesk](http://bibdesk.sourceforge.net) on OS X, distributed with [MacTeX](https://www.tug.org/mactex/).)
1. Run `rake`.
1. Enjoy `master.pdf`.

## Todo

- Add [`subfiles` support](https://en.wikibooks.org/wiki/LaTeX/Modular_Documents#Separate_compilation_of_child_documents) for separate compilation of individual document sections
- Add `$use_bibtex` option to top of rakefile so you can easily turn it off if desired (?)
    - Don't create tasks if the flag is `false`
