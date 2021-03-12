---
layout: post
title: Bash Help to Complete
description: Script that builds tab-completion configurations from --help output
date: 2021-03-12 15:18:45 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a set of Git utilities for aliasing commands with wrapper scripts. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...



**Clone**


```Bash
mkdir -p ~/git/hub/bash-utilities

cd ~/git/hub/bash-utilities

git clone --recurse-submodules git@github.com:bash-utilities/help-to-complete.git
```


**Install**


```Bash
cd ~/git/hub/bash-utilities/help-to-complete

make install
```


**Usage**


After installing `bash-help-to-complete` the any script within the `alias-scripts/` directory may be installed by name, eg...


```Bash
sudo help-to-complete --executable script-name\
                      --completion-dir /usr/share/bash-completion/completions\
                      --help-option '--usage'
```



[link__documentation]: https://github.com/git-utilities/link-alias/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/git-utilities/link-alias "Repository source code"

