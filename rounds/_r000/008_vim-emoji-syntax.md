---
layout: post
title: Vim Emoji Syntax
description: Vim syntax for emoji conceal characters
date: 2020-08-16 15:53:55 -0700
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


Check the [documentation][documentation__emoji_syntax] for detailed getting started and usage instructions, the [source code][source__emoji_syntax] is available on GitHub.



[documentation__emoji_syntax]: https://github.com/vim-utilities/emoji-syntax/blob/main/.github/README.md "Repository documentation"

[source__emoji_syntax]: https://github.com/vim-utilities/emoji-syntax "Repository source code"

