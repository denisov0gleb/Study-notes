# Math in LaTeX files #

Created 07.01.21 by **DGL**

Modified 07.01.21 by **DGL**

# Table of Content:

<!-- vim-markdown-toc GFM -->

1. [Equations environment](#equations-environment)
1. [Symbols](#symbols)

<!-- vim-markdown-toc -->

# Equations environment #
[Table of Content](#table-of-content)


```latex
% In-text equation:
$ ... $


% Centered equation:
$$ ... $$


% Equations environment:
\begin{equation}
	%...
\end{equation}


\begin{eqnarray}
	%long string of equation
	%or many lines
\end{eqnarray}

%Systems
$\begin{cases}
	4x + 3y = 6\\
	6x - 5y + 29= 0
\end{cases}$
```


# Symbols #
[Table of Content](#table-of-content)

[Detect the hand written symbol](http://detexify.kirelabs.org/classify.html)

```latex
\usepackage{amsfonts}
\usepackage{amssymb}

% Grad symbol:
^\circ

%MxN:
\times

%Brackets
(\big (\Big (\bigg (\Bigg

% /
{\slash}

% ...
\ldots

% +-
\pm

% >=
\geqslant

% <=
\leqslant
```



№ symbol in russian text

```latex
\usepackage{textcomp}

\newcommand*{\No}{\textnumero}

\No 1
```
