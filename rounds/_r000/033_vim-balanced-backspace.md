---
layout: post
title: Vim Balanced Backspace
description: Attempts to balance removal of quotes and braces
date: 2021-02-11 16:42:23 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a Vim plugin for balanced removal of quotes and braces. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Install**


```bash
mkdir -vp ~/git/hub/vim-utilities

cd ~/git/hub/vim-utilities

git clone git@github.com:vim-utilities/balanced-backspace.git

cd ~/git/hub/vim-utilities/balanced-backspace

make install
```


**Usage**


- `{<BS>}` Backspace within empty curly-brace will delete the closing brace along with opening brace

- `(<BS>)` Backspace within empty parenthesis will delete the closing parenthesis along with opening parenthesis

- `[<BS>]` Backspace within empty square-braces will delete the closing brace along with opening brace

- `"<BS>"` Backspace within empty double-quotes will delete the closing quote along with opening quote

- `'<BS>'` Backspace within empty single-quotes will delete the closing quote along with opening quote

- ``<BS>`` Backspace within empty backtick will delete the closing backtick along with opening backtick



[link__documentation]: https://github.com/vim-utilities/balanced-backspace/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/vim-utilities/balanced-backspace "Repository source code"

