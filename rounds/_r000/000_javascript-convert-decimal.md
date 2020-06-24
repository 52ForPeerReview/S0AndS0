---
layout: post
title: JavaScript convert decimal
description: Converts decimal to another base, eg. hex, octal, or binary
date: 2020-06-21 14:12:58 -0700
date_updated: 2020-06-23 20:12:58 -0700
time_to_live: 1800
---



This week I'll be publishing a JavaScript module that converts any decimal integer to another base; eg. hex, octal, or binary. By default it will allow for bases as large as `36`, and if possible I'll also enable options for increasing the base size as well as modifying symbols used for conversion.


Example of expected usage...


```javascript
decimalToBase(10, 16);
//> "0xA"

decimalToBase(10, 8);
//> "0o12"

decimalToBase(10, 2);
//> "0b1010"
```


## Update
[heading__update]: #update "Updates about publishing project"


{% assign date_format = site[site.theme].date_format | default: "%b %-d, %Y" %}

As of {{ page.date_updated | date: date_format }} this project is now live!


Clone via...


```bash
git clone git@github.com:javascript-utilities/decimal-to-base.git
```


Documentation is currently within the [`ReadMe`][documentation__decimal_to_base] file, [source code][source__decimal_to_base] may be perused on GitHub, and a [live demo][demo__decimal_to_base] is available for testing thanks to GitHub Pages.



[documentation__decimal_to_base]: https://github.com/javascript-utilities/decimal-to-base/blob/main/.github/README.md "Repository documentation"

[source__decimal_to_base]: https://github.com/javascript-utilities/decimal-to-base "Repository source code"

[demo__decimal_to_base]: https://javascript-utilities.github.io/decimal-to-base/index.html "Live and interactive demo"
