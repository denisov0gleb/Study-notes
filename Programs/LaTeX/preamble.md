# Preamble in LaTeX files #

Created 07.01.21 by **DGL**

Modified 07.01.21 by **DGL**

# Table of Content:

<!-- vim-markdown-toc GFM -->

1. [Simple preamble example](#simple-preamble-example)
1. [Document class](#document-class)
1. [Page geometry](#page-geometry)
	1. [Landscape orientation](#landscape-orientation)
	1. [Columns in page](#columns-in-page)
	1. [Footer and header](#footer-and-header)
		1. [Footer and header example](#footer-and-header-example)

<!-- vim-markdown-toc -->

# Simple preamble example #
[Table of Content](#table-of-content)

```latex
\usepackage[utf8]{inputenc}
\usepackage[T1, T2A]{fontenc}
\usepackage[english, russian]{babel}
\usepackage[warn]{mathtext}
\usepackage{amsmath}
%\usepackage{amsfonts}
\usepackage{amssymb}

\usepackage{graphicx}

\graphicspath{ {/}}
\usepackage[version=4]{mhchem}
\usepackage{enumerate}
\usepackage{fancybox, fancyhdr}


\usepackage[left=25mm, top=20mm, right=20mm, bottom=20mm]{geometry}
%\textheight=28cm			% высота текста A4
%\textwidth=18cm				% ширина текста A4
%\oddsidemargin=0pt			% отступ от левого края
%\topmargin=0cm			% отступ от верхнего края
\parindent=0pt				% абзацный отступ
\parskip=0pt				% интервал между абзацами
\tolerance=2000				% терпимость к "жидким" строкам
\flushbottom				% выравнивание высоты страниц
\setcounter{secnumdepth}{0}	% секции без нумерации
```


In file add `\input{preamble}`.


# Document class #
[Table of Content](#table-of-content)

```latex
\documentclass[12pt, a4paper, oneside]{report}	% {article|letter|report}
```

# Page geometry #
[Table of Content](#table-of-content)

```latex
\usepackage{geometry}
\geometry
{
	a4paper,
	left=20mm,
	right=20mm,
	top=25mm,
	bottom=20mm,
	headheight=10pt,
	footskip=20pt
}
```

 *or*

```latex
\textheight=28cm			% высота текста A4
\textwidth=16cm				% ширина текста A4
\oddsidemargin=0pt			% отступ от левого края
\topmargin=0cm			% отступ от верхнего края

\parindent=0pt				% абзацный отступ
\parskip=0pt				% интервал между абзацами
\tolerance=2000				% терпимость к "жидким" строкам
\flushbottom				% выравнивание высоты страниц
\setcounter{secnumdepth}{0}	% секции без нумерации
```


## Landscape orientation ##
[Table of Content](#table-of-content)

```latex
\usepackage{lscape}

\begin{landscape}

	Landscape text in \LaTeX.

\end{landscape}
```


## Columns in page ##
[Table of Content](#table-of-content)

```latex
\usepackage{multicol}

\setlength{\columnsep}{1.5cm} % separation distance between columns

\setlength{\columnseprule}{0.4pt} % vertical separation line and it's width

\usepackage{color}
\def\columnseprulecolor{\color{blue}} % separation line color

\begin{document}
\begin{multicols}{2}

	First column

\columnbreak

	Second column

\end{multicols}

```


## Footer and header ##
[Table of Content](#table-of-content)

```latex
\usepackage{fancybox, fancyhdr}
```

```latex
\fancypagestyle{firststyle} %новый стиль
{
	\fancyfootoffset[R]{-12cm} %так можно регулировать ширину колонтитула
	% ...
	\renewcommand{\footrulewidth}{0.3 mm} %толщина отделяющей полоски снизу
	\renewcommand{\headrulewidth}{0.3 mm} %толщина отделяющей полоски сверху
}

\begin{document}
\thispagestyle{firststyle}
```

### Footer and header example ###

```latex
\pagestyle{fancy}
\fancyhead[L]{{\small Подготовлено для Игната, 08.04.20}}
\fancyhead[R]{{\small denisov0gleb@gmail.com}}

%\fancyhead{} % Clear the header

%E: Even page (чётная страница)
%O: Odd page (нечётная страница)
%L: Left field (левое поле)
%C: Center field (центральное поле)
%R: Right field  (правое поле)
%H: Header  (верхний колонтитул)
%F: Footer   (нижний колонтитул)
\fancyhead[*]{}
\fancyfoot[*]{}

\fancyfoot[C]{-~\thepage~-}

% Delete the line of header/footer
\renewcommand{\headrulewidth}{0pt}
```
