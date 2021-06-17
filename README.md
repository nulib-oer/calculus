# Calculus OER Project

**By Aaron Greicius and Sean McAfee**

This repository contains the source files for an OER textbook on Single-variable calculus. The source files are written for processing by [PreTeXt](https://pretextbook.org/). PreTeXt is included in this repository as a [git submodule](https://www.atlassian.com/git/tutorials/git-submodule). 

## Getting Started

PreTeXt provides [documentation](https://pretextbook.org/documentation.html) on installing required software based on your operating system. You'll need the following software installed on your machine:

- a text editor (e.g. [VS Code](https://code.visualstudio.com/), [Sublime Text](https://www.sublimetext.com/), etc.)
- [Git](https://git-scm.com/) version control system
- a LaTeX distribution (e.g. [TeX Live](https://www.tug.org/texlive/), [MacTeX](https://www.tug.org/mactex/), [MikTex](https://miktex.org/), [TinyTeX](https://yihui.org/tinytex/))
- and an [XSLT processor](http://www.xmlsoft.org/xslt/xsltproc.html).

Download this repository to your computer from the command-line:

```sh
git clone https://github.com/nulib-oer/calculus.git
```

Generate HTML for single-variable calculus:

```sh
xsltproc -xinclude pretext/xsl/pretext-html.xsl single-variable/index.xml
```