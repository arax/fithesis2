FIThesis2
=========
This repository is a fork of http://is.muni.cz/th/173173/fi_b?lang=en

## Installation

### Local
* Copy the content of this repository to a directory containing your \*.tex files

### System-wide
* Copy the content of this repository to a location where `kpathsea` can find it and run `texhash` or `mktexlsr`

~~~
# An example for Debian/Ubuntu based distros with TeXLive
sudo cp -R fithesis2 /usr/share/texmf/tex/latex
sudo mkdir -p /usr/share/texmf/metafont/fithesis2
sudo cp fithesis2/loga/fi-logo.mf /usr/share/texmf/metafont/fithesis2/fi-logo.mf
sudo texhash
~~~

## Usage

~~~
%% Load document class fithesis2
%% {10pt, 11pt, 12pt}
%% {draft, final}
%% {oneside, twoside}
%% {onecolumn, twocolumn}
\documentclass[11pt,draft,oneside]{fithesis2}

%% Basic packages
\usepackage[english]{babel}
\usepackage{cmap}
\usepackage[T1]{fontenc}
\usepackage{lmodern}
\usepackage[utf8]{inputenc}
\usepackage{graphicx}

%% Additional packages for colors, advanced
%% formatting options, etc.
\usepackage{color}
\usepackage{microtype}
\usepackage{url}
\usepackage{cslatexquotes}
\usepackage{fancyvrb}
\usepackage[small,bf]{caption}
\usepackage[plainpages=false,pdfpagelabels,unicode]{hyperref}
\usepackage[all]{hypcap}

%% Fix long URLs in DVIs
\usepackage{ifpdf}

\ifpdf
\else
  \usepackage{breakurl}
\fi

%% Packages used to generate various lists
\usepackage{makeidx}
\makeindex

\usepackage[xindy]{glossaries}
\makeglossary

%% Use STAR and CIRCLE signs for nested
%% itemized lists
\renewcommand{\labelitemii}{$\star$}
\renewcommand{\labelitemiii}{$\circ$}

%% Title page information
\thesistitle{Thesis title}
\thesissubtitle{Master's thesis}
\thesisstudent{Generic Name}
\thesiswoman{false} %% Important when using Slovak or Czech lang
\thesisfaculty{fi}  %% {fi, eco, law, sci, fsps, phil, ped, med, fss}
\thesislang{en}     %% {en, sk, cs}
\thesisyear{Spring 2013}
\thesisadvisor{prof. Generic Advisor}

%% Beginning of the document
\begin{document}

%% Front page with a logo and basic thesis information
\FrontMatter
\ThesisTitlePage

%% Thesis declaration (required)
\begin{ThesisDeclaration}
  \DeclarationText
  \AdvisorName
\end{ThesisDeclaration}

%% Thanks (optional)
\begin{ThesisThanks}
My thanks go to ... 
\end{ThesisThanks}

%% Abstract (required)
\begin{ThesisAbstract}
This thesis is about ...
\end{ThesisAbstract}

%% Keywords (required)
\begin{ThesisKeyWords}
GitHub, Thesis, Key, Words, Specific, ...
\end{ThesisKeyWords}

%% Beginning of the thesis itself
\MainMatter

%% TOC (required)
\tableofcontents

%% Thesis text structured using
%% chapters, sections, subsections, etc.
\chapter{Intro}

%% Lists of tables and figures, glossary, etc.
\printindex
\printglossary
\listoffigures
\listoftables

%% Bibliography from references.bib
\bibliographystyle{plain}
\bibliography{references}

%% Additional materials
\appendix

%% End of the whole document
\end{document}
~~~

## Credits

* Jan Pavlovič (fithesis)
* Stanislav Filipčík (fithesis2)
