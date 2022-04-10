---
layout: post
title: Git Link Alias
description: Collection of scripts for Git aliasing
date: 2021-02-26 11:05:08 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a set of Git utilities for aliasing commands with wrapper scripts. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Clone**


```Bash
mkdir -p ~/git/hub/git-utilities

cd ~/git/hub/git-utilities

git clone --recurse-submodules git@github.com:git-utilities/link-alias.git
```


**Install**


```Bash
cd ~/git/hub/git-utilities/link-alias

make install
```


**Usage**


After installing `git-link-alias` the any script within the `alias-scripts/` directory may be installed by name, eg...


```Bash
git link-alias init
```



[link__documentation]: https://github.com/git-utilities/link-alias/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/git-utilities/link-alias "Repository source code"

[link__tweet]: https://twitter.com/S0_And_S0/status/1365378976194179078

