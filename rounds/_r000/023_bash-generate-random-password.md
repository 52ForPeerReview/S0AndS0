---
layout: post
title: Bash Generate Random Password
description: Generates random passphrase of given length
date: 2020-12-04 11:36:55 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a project for generating random password of a given length. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub; the TLDR (quick-start) is as follows...


**Clone**


```bash
cd /usr/local/etc

sudo git clone https://github.com/paranoid-linux/generate-random-password.git
```


**Install**


```bash
cd /usr/local/etc/generate-random-password

sudo make install
```


**Usage**


```bash
generate-random-password 32 42
#> gbMCn>cC^OzF1/!9`sx0h|@9&f}YZ?B?4<+m(v>&XE
```


[link__documentation]: https://github.com/paranoid-linux/generate-random-password/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/paranoid-linux/generate-random-password "Repository source code"

