---
layout: post
title: Vim Emoji Syntax
description: Vim syntax for emoji conceal characters
date: 2020-08-09 15:53:55 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I have published a Vim syntax and set of scripts that replace Emoji hex Unicode and word codes with symbols via `cchar`, eg...


```markdown
Fancy :tophat:
```


... will result in something similar to...


> Fancy 🎩


... while editing MarkDown files. Note, this does **not** modify the document but instead the buffer while viewing/writing within Vim.


Check the [documentation][documentation__to_unicode] for detailed getting started and usage instructions, the [source code][source__to_unicode] is available on GitHub.



[documentation__to_unicode]: https://github.com/vim-utilities/emoji-syntax/blob/main/.github/README.md "Repository documentation"

[source__to_unicode]: https://github.com/vim-utilities/emoji-syntax "Repository source code"

