# Easy CRediT statement for TeX

This repository provides a pandoc template for easily compiling CRediT statements for TeX documents.

The template can be used to generate either a section to be included, e.g., in the appendix of a paper, or a stand-alone PDF document.

The layout of the "section" version is optimized for double-column paper format. The layout of the "stand-alone" version is (very) simplistic.

## Description

The CRediT data is stored in `credit.yml`. The field names should be fairly self-explanatory.

> I have a personal pipeline to easily generate and copy the contributions into the template file, but that's beyond the scope of this repo.

Using pandoc with the commands provided below, one can easily generate a well-formated statement, either as a section to be included in a TeX document, or as a stand-alone PDF file.

## Requirements

* Pandoc
* LaTeX

## Usage

### TeX Section

For generating the statement as a TeX section:

```bash
pandoc credit.yml -f markdown --template credit -o credit.tex
```

In your main TeX documents, use the following:

```latex
% in your header, add the following packages (if not present already):
\usepackage{tabularx}
\usepackage{fontawesome5}

% wherever you want to use the credits (e.g. after \appendix) add:
\input{credit.tex}
```

### Standalone PDF

For generating the statement as stand-alone PDF file:

```bash
pandoc credit.yml -f markdown --template credit -M stand-alone -o credit.pdf
```
