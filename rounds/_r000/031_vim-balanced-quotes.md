---
layout: post
title: Vim Balanced Quotes
description: Balances quotes and backticks in unobtrusive ways
date: 2021-01-28 20:14:29 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a Vim plugin for balancing inserted quotes and backticks. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Clone**


```bash
mkdir -vp ~/git/hub/vim-utilities

cd ~/git/hub/vim-utilities

git clone git@github.com:vim-utilities/balanced-quotes.git
```


**Install**


```bash
cd ~/git/hub/vim-utilities/balanced-quotes

make install
```


**Usage**


While in Insert mode quotes will have the following behavior:


- **'** Open single-quote; automatically inserts a closing quote, and moves cursor left by one column

- **"** Open double-quote; automatically inserts a closing quote, and moves cursor left by one column

- **\`** Open backtick; automatically inserts a closing backtick, and moves cursor left by one column



[link__documentation]: https://github.com/vim-utilities/balanced-quotes/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/vim-utilities/balanced-quotes "Repository source code"

