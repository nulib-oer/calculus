# Calculus OER Project

**By Aaron Greicius and Sean McAfee**

This repository contains the source files for an OER textbook on Single-variable calculus. The source files are written for processing by [PreTeXt](https://pretextbook.org/). PreTeXt is included in this repository as a [git submodule](https://www.atlassian.com/git/tutorials/git-submodule). 

## Getting Started

PreTeXt provides [documentation](https://pretextbook.org/documentation.html) on installing required software based on your operating system. You'll need the following software installed on your machine:

- a text editor (e.g. [VS Code](https://code.visualstudio.com/), [Sublime Text](https://www.sublimetext.com/), etc.)
- [Git](https://git-scm.com/) version control system
- a LaTeX distribution (e.g. [TeX Live](https://www.tug.org/texlive/), [MacTeX](https://www.tug.org/mactex/), [MikTex](https://miktex.org/), [TinyTeX](https://yihui.org/tinytex/))
- and an [XSLT processor](http://www.xmlsoft.org/xslt/xsltproc.html).

## Get the Files

Use Git to download the files and contribute back to the project. Git is a command line program you'll run from a terminal. Here are the commands: 

_Download the repository:_

```sh
git clone https://github.com/nulib-oer/calculus.git
```

_Change directories into your local copy:_

```
cd calculus
```

_Download the PreTeXt files:_

```
git submodule init
git submodule update
```

## Edit the Files

Open the project folder in a text editor. The book files for _Single-variable Calculus_ are in the `/single-variable/` folder. The book is divided into two parts: Differential (`/differential/`) and Integral (`/integral/`). Write or edit chapters and sections for each part within the appropriate subdirectory. 

The book's compiliation is managed in the `index.xml` file. Any new chapters need to be included in the `index.xml` file. 

Save your edits in your text editor as you would normally (e.g. Control + S).

## Generate HTML from PreTeXt source

The `xsltproc` command requires two arguments to generate HTML from PreTeXt/XMl source. The first argument is a relative path to an `.xsl` file in the `pretext/` folder that manages the transformation from XML to HTML, and the second argument is the XML file you'd like to transform. 

Since we're making a book, we're beginning with an `index.xml` that defines the book's container and references many files to _include_ during the HTML processing. This is the file we want to use as our second argument.

```
xsltproc pretext/xsl/pretext-html.xsl single-variable/index.xml
```

We'll also need to use two options from the `xsltproc` software that go before the two arguments:

- `-xinclude`: lets us reference other files from the `index.xml` file to _include_ in the generated HTML
- `-o ./single-variable/public/`: define an output directory for our generated HTML files to be saved to after the transformation. 

Here's the full command for building the _Single-variable Calculus_ book:

```
xsltproc -xinclude -o ./single-variable/public/ pretext/xsl/pretext-html.xsl single-variable/quickstart.xml
```

## Contribute Edits Back to the Project

Git will notice when new files are added, or existing files are edited or deleted. These edits need to be formally added to the Git's version history. 

You can select individual files to formally add to the git repository history:

```
git add single-variable/differential/file.xml
```

Or you can add all of the edits:

```
git add .
```

Next, you'll need to make a commit, which represents a snapshot of the project in a specific moment in time. Commits require messages that will be recorded to a log. These messages are notes to yourself, and anyone else who might be contributing to the project or using the project files in the future.

```
git commit -m "new chapters"
```

Now that your edits have been committed to your _local_ repository, they need to be pushed up to the remote repository for others to see your edits. This command will push your new commit(s) to the `origin` repository (i.e. this one on GitHub) from your `main` branch (which is the default branch name used by GitHub).

```
git push origin main
```

Conversely, you may be aware that others may be contributing edits to the project. You can sync your _local_ copy with the remote by pulling in the changes:

```
git pull
```

It's a good idea to run this command each time you begin to work on the project.