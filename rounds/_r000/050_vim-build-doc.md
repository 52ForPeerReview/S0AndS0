---
layout: post
title: Vim Build Doc
description: Copies, and customizes, documentation file to target path
date: 2021-06-09 13:57:52 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a project for building Vim plugin documentation files. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Clone**


```bash
mkdir -vp ~/git/hub/vim-utilities

cd ~/git/hub/vim-utilities

git clone git@github.com:vim-utilities/build-vim-doc.git
```


**Install**


```bash
cd ~/git/hub/vim-utilities/build-vim-doc

make install
```


**Usage**


Make a directory for Vim new documentation file...


```bash
mkdir -p ~/git/hub/vim-utilities/project-name/doc
```


Run `build-vim-doc` script to initialize a new documentation file...


```bash
build-vim-doc --path ~/git/hub/vim-utilities/project-name\
              --name script-file.vim\
              --mode Visual
              --author S0AndS0\
              --version 8.2
```



[link__documentation]: https://github.com/vim-utilities/build-vim-doc/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/vim-utilities/build-vim-doc "Repository source code"

