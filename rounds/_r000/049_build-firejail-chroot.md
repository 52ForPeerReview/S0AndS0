---
layout: post
title: Build FireJail Chroot
description: Initializes new chroot file systems compatible with Firejail sandboxing utility
date: 2021-06-03 13:20:41 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a project for initializing new chroot file systems compatible with Firejail sandboxing utility. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Clone**


```bash
cd /usr/local/etc

sudo git clone https://github.com/paranoid-linux/build-firejail-chroot.git
```


**Install**


```bash
cd /usr/local/etc/build-firejail-chroot

sudo make install
```


**Usage**


```bash
build-firejail-chroot --help
```


[link__documentation]: https://github.com/paranoid-linux/build-firejail-chroot/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/paranoid-linux/build-firejail-chroot "Repository source code"

