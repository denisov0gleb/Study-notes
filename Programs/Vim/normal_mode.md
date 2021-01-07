# Insert mode in Vim #

Created 07.01.21 by **DGL**

Modified 07.01.21 by **DGL**


# Table of Content:

<!-- vim-markdown-toc GFM -->

1. [Normal Mode](#normal-mode)

<!-- vim-markdown-toc -->

# Normal Mode #

| Command        | Description                                  |
| ---            | ---                                          |
| ga             | show the information about symbol            |
| ]s             | next spelling error                          |
| [s             | previous spelling error                      |
| zg             | add the word under cursor to the dictionary  |
| zug            | undo `zg` command                            |
| z=             | print list of possible variants              |
| zo             | open foldings                                |
| zc             | close foldings                               |
|                |                                              |
| g~             | toggle case under cursor (+**Visual**)       |
| g~~            | toggle case of the current line              |
| g~$            | toggle case of the current line till the end |
| gUU            | switch to upper case                         |
| guu            | switch to lower case                         |
|                |                                              |
| Ctrl-G         | show info about file                         |
|                |                                              |
| Ctrl-R / .     | redo                                         |
|                |                                              |
| Ctrl-W o       | `:only`                                      |
| Ctrl-W n       | `:new`                                       |
| Ctrl-W c       | `:q`                                         |
| Ctrl-W s       | `:split`                                     |
| Ctrl-W v       | `:vsplit`                                    |
| Ctrl-W r       | swap bottom/top windows                      |
| Ctrl-W _       | max height                                   |
| Ctrl-W \       | max width                                    |
| Ctrl-W =       | normalize all windows                        |
| Ctrl-W # >     | increase to right for # value                |
| Ctrl-W # <     | increase to left for # value                 |
| Ctrl-W # +     | increase height for # value                  |
| Ctrl-W # -     | decrease height for # value                  |
| Ctrl-W H/J/K/L | move splitted windows                        |
