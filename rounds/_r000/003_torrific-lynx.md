---
layout: post
title: Torrific Lynx
description: Enables clear-net browsing over the Tor network via Lynx web browser
date: 2020-07-12 15:16:04 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I have published a Bash script that enables clear-net browsing over the Tor network via Lynx web browser.



Check the [documentation][documentation__torrific_lynx] for detailed getting started and usage instructions, the TLDR is...


- Make a directory for Git repository...


```bash
mkdir -vp git/hub/paranoid-linux
```


- Change current working directory and clone repository with Submodule dependencies...


```bash
cd git/hub/paranoid-linux

git clone --recurse-submodules git@github.com:paranoid-linux/torrific-lynx.git
```


- _Install_ via symbolic link...


```bash
cd git/hub/paranoid-linux/torrific-lynx

ln -s "${PWD}/torrific-lynx" "${HOME}/bin/"
```


- Pass a URL on the command-line to start Lynx and load that site...


```bash
torrific-lynx 'https://duckduckgo.com'
```



[documentation__torrific_lynx]: https://github.com/paranoid-linux/torrific-lynx/blob/main/.github/README.md "Repository documentation"

[source__torrific_lynx]: https://github.com/paranoid-linux/torrific-lynx "Repository source code"

[question__code_review__stack_exchange]: https://codereview.stackexchange.com/questions/245501/clear-net-browsing-with-lynx-over-tor
