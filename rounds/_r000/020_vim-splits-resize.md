---
layout: post
title: Vim Splits Resize
description: Use Alt or Esc with direction keys to re-size splits
date: 2020-11-12 17:36:22 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a Vim plugin for re-sizing splits. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub...


**Clone**


```bash
mkdir -vp ~/git/hub/vim-utilities

cd ~/git/hub/vim-utilities

git clone git@github.com:vim-utilities/splits-resize.git
```


**Install**


```bash
cd ~/git/hub/vim-utilities/splits-resize

make install
```


**Usage**


- `<ESC>h` or `<A-h>`, re-size active vertical split by `-2`

- `<ESC>j` or `<A-j>`, re-size active horizontal split by `+2`

- `<ESC>k` or `<A-k>`, re-size active horizontal split by `-2`

- `<ESC>l` or `<A-l>`, re-size active vertical split by `+2`



[link__documentation]: https://github.com/vim-utilities/splits-resize/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/vim-utilities/splits-resize "Repository source code"

