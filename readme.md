# LaTeX + rake prototype

## What is this?

A handful of `.tex` files, plus a `Rakefile`, so you can quickly get started writing a beautifully-typset and fully-cited paper.

## What is LaTeX?

Text and code go in, pretty document comes out.

[Read this](https://en.wikibooks.org/wiki/LaTeX); it's everything you need to know.

Get it from [TeX Live](http://tug.org/texlive/), or [MacTeX for OS X](https://www.tug.org/mactex/).

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

- Add `$use_bibtex` option to top of rakefile so you can easily turn it off if desired (?)
    - Don't create tasks if the flag is `false`
