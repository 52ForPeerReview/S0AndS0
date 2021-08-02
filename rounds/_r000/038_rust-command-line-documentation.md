---
layout: post
title: Rust Command-Line Documentation
description: Builds/finds documentation for Rust package or library
date: 2021-03-18 11:43:52 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a Bash script for building and displaying Rust documentation via the command-line. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...



**Clone**


```bash
mkdir -p ~/git/hub/rust-utilities

cd ~/git/hub/rust-utilities

git clone --recurse-submodules git@github.com:rust-utilities/cli-rustdoc.git
```


**Install**


```bash
cd ~/git/hub/rust-utilities/cli-rustdoc

make install
```


**Usage**


After installing `cli-rustdoc` run the script with a package name...


```bash
cli-rustdoc 'version_operators'
```



[link__documentation]: https://github.com/rust-utilities/rust-utilities/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/rust-utilities/rust-utilities "Repository source code"

[link__tweet]: https://twitter.com/S0_And_S0/status/1372657551414804484

