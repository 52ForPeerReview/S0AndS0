---
layout: post
title: Vim MarkDown Surrounds
description: Toggles MarkDown elements; bold, italic, and strike-through
date: 2020-12-11 15:48:07 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a Vim plugin toggling bold, italic, and strike-through elements within MarkDown files. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Clone**


```bash
mkdir -vp ~/git/hub/vim-utilities

cd ~/git/hub/vim-utilities

git clone git@github.com:vim-utilities/markdown-surrounds.git
```


**Install**


```bash
cd ~/git/hub/vim-utilities/markdown-surrounds

make install
```


**Usage**


Normal mode default maps are provided for toggling bold, italic, and strike-through state; either for the current word, or line, that the cursor is on.


- `<Leader>`<kbd>b</kbd> toggle bold state of word under cursor.

- `<Leader>`<kbd>B</kbd> toggle bold state of line under cursor.

- `<Leader>`<kbd>i</kbd> toggle italic state of word under cursor.

- `<Leader>`<kbd>I</kbd> toggle italic state of line under cursor.

- `<Leader>`<kbd>st</kbd> toggle strike-through state of current word.

- `<Leader>`<kbd>ST</kbd> toggle strike-through state current line.



[link__documentation]: https://github.com/vim-utilities/markdown-surrounds/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/vim-utilities/markdown-surrounds "Repository source code"

