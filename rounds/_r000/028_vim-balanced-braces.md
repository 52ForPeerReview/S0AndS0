---
layout: post
title: Vim Balanced Braces
description: Attempts to balance parentheses and curly/square-braces
date: 2021-01-08 10:57:21 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a Vim plugin for balancing inserted parentheses and brackets. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Clone**


```bash
mkdir -vp ~/git/hub/vim-utilities

cd ~/git/hub/vim-utilities

git clone git@github.com:vim-utilities/balanced-braces.git
```


**Install**


```bash
cd ~/git/hub/vim-utilities/balanced-braces

make install
```


**Usage**


While in Insert mode open/close curly-braces, parentheses, and square-brackets will have the following behavior:


- `{` Open curly-brace; automatically insert a closing curly-brace, and move the cursor left by one column

- `}` Close curly-brace; optionally move the cursor right by one column, if currently on a closing curly-brace, or insert closing curly-brace


- `(` Open parenthesis; automatically insert a closing parenthesis, and move the cursor left by one column

- `)` Close parenthesis; optionally move the cursor right by one column, if currently on a closing parenthesis, or insert closing parenthesis


- `[` Open square-bracket; automatically insert a closing square-bracket, and move the cursor left by one column

- `]` Close square-bracket; optionally move the cursor right by one column, if currently on a closing square-bracket, or insert closing square-bracket



[link__documentation]: https://github.com/vim-utilities/balanced-braces/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/vim-utilities/balanced-braces "Repository source code"

