FrenchLaTeXReportModel
======================

### Description
This latex document class provides a model for student french report.

### Tutorial

## Package declaration (put the above code before \begin{document})
# Packages for equation
\usepackage{amsmath}
\usepackage{amssymb}
\usepackage{mathrsfs}

# Packages for source code
\usepackage{sourcecode}
\lstset{language=Java}
	# /!\ For some languages (like R language), this is necessary to surround the \lstset command by these lines :
	\shorthandoff{!}
	\lstset{language=R}
	\shorthandon{!}

## Document content (put the above code after \begin{document})
# First page
\maketitle
\newpage
	# /!\ You have to change the config file according to your specific informations
	\author{Pierre} % Author name
	\title{Pidupuis model} % Report title
	\subtitle{A french {\LaTeX} report model} % Report subtitle
	\llogo{img/autruche.jpg}{0.2} % Top left logo
	\clogo{img/autruche.jpg}{0.2} % Top center logo
	\rlogo{img/autruche.jpg}{0.2} % Top right logo
	\banner{img/autruche.jpg}{0.5} % Big center picture

# Table of contents
\tableofcontents[Contents] % Without argument, the title will be 'Sommaire'

# List of figures
\listoffigures[Figures] % Without argument, the title will be 'Liste des figures'

# Bibliography
\nocite{*} % Bibliographie
\bibliographystyle{plain}
\renewcommand{\bibname}{References}
\bibliography{modele}
	# /!\ You need to create a .bib file which contains the bibliography informations
	# This .bib file needs to be called as the main latex file (i.e. modele.bib for modele.tex)
	# To use it, you need to use the unix command : bibtex modele (without extension) between to pdflatex compilation

# File including
\include{include/export}
	# /!\ You have to include .tex file without precising the file extension
	# In this example this is the including of export.tex file
	# This is typically the file which is generated by convert a google doc to a latex file by using the script created by gcornut and me

# Title
\chapter{Exemple de chapitre}
\section{Exemple de section}
\subsection{Exemple de section}
\subsubsection{Exemple de section}

# Figure
\fig{img/autruche.jpg}{0.4}{Autruche}

# Item list
\begin{itemize}
\item Premiere puce
\item Deuxieme puce
\end{itemize}

# Equation
\begin{center}
 $IC = [ m \pm 2.262 \times \frac{s}{\sqrt{n}} ]$ \par
\end{center}

# Source code
\vspace*{5mm} \begin{lstlisting}
> qt(c(0.975), df=9, lower.tail=TRUE)
[1] 2.262157
\end{lstlisting}

