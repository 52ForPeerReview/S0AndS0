---
layout: post
title: Vim Build Makefile
description: Copies, and customizes, Makefile script to target path
date: 2021-03-30 16:17:15 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a project for building a Makefile for Vim plugin installation. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Clone**


```Bash
mkdir -vp ~/git/hub/vim-utilities

cd ~/git/hub/vim-utilities

git clone git@github.com:vim-utilities/build-vim-makefile.git
```


**Install**


```Bash
cd ~/git/hub/vim-utilities/build-vim-makefile

make install
```


**Usage**


Make a directory for Vim new plugin project...


```Bash
mkdir -p ~/git/hub/vim-utilities/project-name
```


Run `build-vim-makefile` script for new project...


```Bash
build-vim-makefile --path ~/git/hub/vim-utilities/project-name\
                   --author "S0AndS0"\
                   --version "0.0.1"
```



[link__documentation]: https://github.com/vim-utilities/build-vim-makefile/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/vim-utilities/build-vim-makefile "Repository source code"

