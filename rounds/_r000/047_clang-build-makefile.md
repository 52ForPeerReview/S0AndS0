---
layout: post
title: CLang Build Makefile
description: Copies and customizes Makefile script to target path
date: 2021-05-16 19:57:55 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a project for building a Makefile for C-Lang project installation. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Clone**


```bash
mkdir -vp ~/git/hub/clang-utilities

cd ~/git/hub/clang-utilities

git clone --recurse-submodules git@github.com:clang-utilities/build-clang-makefile.git
```


**Install**


```bash
cd ~/git/hub/clang-utilities/build-clang-makefile

make install
```


**Usage**


Make a directory for C-Lang new plugin project...


```bash
mkdir -p ~/git/hub/clang-utilities/project-name
```


Run `build-clang-makefile` script for new project...


```bash
build-clang-makefile --path ~/git/hub/clang-utilities/project-name\
                     --author "S0AndS0"\
                     --version "0.0.1"
```



[link__documentation]: https://github.com/clang-utilities/build-clang-makefile/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/clang-utilities/build-clang-makefile "Repository source code"

