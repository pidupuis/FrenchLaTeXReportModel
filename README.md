

FrenchLaTeXReportModel
======================

Created by <a href="https://github.com/pidupuis">Pierre DUPUIS</a> - 2012-2013 <br />
This latex document class provides a model which modify the classical report to be closer the french student habits. It also provides a package to easily display source code inside the document. <br />

This document class is fully compatible with a google script created by <a href="https://github.com/gcornut">gcornut</a> and me, which converts the content of a google document to a tex file. See below the "File including" part. 

======================


## Package declaration
Put the code below before \begin{document}
### Packages for equation
> \usepackage{amsmath}<br \>
> \usepackage{amssymb}<br \>
> \usepackage{mathrsfs}

### Packages for source code
> \usepackage{sourcecode}<br \>
> \lstset{language=Java}<br \>

/!\ For some languages (like R language), this is necessary to surround the \lstset command by these lines :<br \>
> \shorthandoff{!}<br \>
> \lstset{language=R}<br \>
> \shorthandon{!}<br \>

## Document content
Put the code below after \begin{document}
### First page
> \maketitle<br \>
> \newpage<br \>

/!\ You have to change the config file according to your specific informations <br \>
> \author{Pierre} % Author name <br \>
> \title{Pidupuis model} % Report title <br \>
> \subtitle{A french {\LaTeX} report model} % Report subtitle <br \>
> \llogo{img/autruche.jpg}{0.2} % Top left logo <br \>
> \clogo{img/autruche.jpg}{0.2} % Top center logo <br \>
> \rlogo{img/autruche.jpg}{0.2} % Top right logo <br \>
> \banner{img/autruche.jpg}{0.5} % Big center picture <br \>

### Table of contents
> \tableofcontents[Contents] % Without argument, the title will be 'Sommaire' <br \>

### List of figures
> \listoffigures[Figures] % Without argument, the title will be 'Liste des figures' <br \>

### Bibliography
> \nocite{*} % Bibliographie <br \>
> \bibliographystyle{plain} <br \>
> \renewcommand{\bibname}{References} <br \>
> \bibliography{modele} <br \>

/!\ You need to create a .bib file which contains the bibliography informations <br \>
This .bib file needs to be called as the main latex file (i.e. modele.bib for modele.tex) <br \>
To use it, you need to use the unix command : bibtex modele (without extension) between to pdflatex compilation <br \>

### File including
> \include{include/export} <br \>

/!\ To include a .tex file, you do not have to precise the file extension. <br \>
In this example this is the including of the export.tex file. This is typically the file which is generated by converting a google doc to a latex file by using the script created by gcornut and me. <br \>

### Title
> \chapter{Exemple de chapitre} <br \>
> \section{Exemple de section} <br \>
> \subsection{Exemple de section} <br \>
> \subsubsection{Exemple de section} <br \>

### Figure
> \fig{img/autruche.jpg}{0.4}{Autruche} <br \>

### Item list
> \begin{itemize} <br \>
> \item Premiere puce <br \>
> \item Deuxieme puce <br \>
> \end{itemize} <br \>

### Equation
> \begin{center} <br \>
> $IC = [ m \pm 2.262 \times \frac{s}{\sqrt{n}} ]$ \par <br \>
> \end{center} <br \>

### Source code
> \vspace*{5mm} \begin{lstlisting} <br \>
> qt(c(0.975), df=9, lower.tail=TRUE) <br \>
> [1] 2.262157 <br \>
> \end{lstlisting} <br \>
