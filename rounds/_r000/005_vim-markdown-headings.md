---
layout: post
title: Vim MarkDown Headings
description: Vim plugin for MarkDown headings
date: 2020-07-26 14:47:07 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I have published my first Vim plugin!


Check the [documentation][documentation__markdown_headings] for detailed getting started and usage instructions; the [source code][source__markdown_headings] is available on GitHub.


For most Linux based distributions the install process _should_ be similar to...


```bash
mkdir -p ~/git/hub/vim-utilities

git clone git@github.com:vim-utilities/markdown-headings.git

cd markdown-headings

./linked-install.sh
```


After installation the documentation can be accessed via Vim's `:help` command, eg...


```vim
:help markdown-heading-transform

:help markdown-heading-link
```



[documentation__markdown_headings]: https://github.com/vim-utilities/markdown-headings/blob/main/.github/README.md "Repository documentation"

[source__markdown_headings]: https://github.com/vim-utilities/markdown-headings "Repository source code"


[question__code_review__stack_exchange]: https://codereview.stackexchange.com/questions/246098/vim-plugin-markdown-headings
