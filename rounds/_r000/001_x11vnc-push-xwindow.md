---
layout: post
title: X11vnc Push XWindow
description: Pushes/mirrors selected XWindow to remote via SSH port forwarding
date: 2020-06-28 15:23:03 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I have published [x11vnc-push-xwindow][source__x11vnc_push_xwindow] which _mirrors_ selected XWindow to remote via SSH port forwarding. It is a _wrapper_ script written in Bash, and intended to enable functionality similar to multi-monitor setups, though it could also be useful for presentations too. Latency is an issue that likely cannot be fully resolved, however, that it is wireless is certainly convenient.


Check the [documentation][documentation__x11vnc_push_xwindow] for detailed getting started and usage instructions, the TLDR is...


- Make a directory for Git repository...


```bash
mkdir -vp git/hub/rpi-curious
```


- Change current working directory and clone repository with Submodule dependencies...


```bash
cd git/hub/rpi-curious

git clone --recurse-submodules git@github.com:rpi-curious/x11vnc-push-xwindow.git
```


- _Install_ via symbolic link...


```bash
cd git/hub/rpi-curious/x11vnc-push-xwindow

ln -s "${PWD}/x11vnc-push-xwindow" "${HOME}/bin/"
```


- Forward local XWindow session to remote SSH host...


```bash
x11vnc-push-xwindow raspberrypi
```



[documentation__x11vnc_push_xwindow]: https://github.com/rpi-curious/x11vnc-push-xwindow/blob/main/.github/README.md "Repository documentation"

[source__x11vnc_push_xwindow]: https://github.com/rpi-curious/x11vnc-push-xwindow "Repository source code"

[question__code_review__stack_exchange]: https://codereview.stackexchange.com/questions/244765/bash-script-to-mirror-xwindow-to-remote-ssh-host
