---
layout: post
title: JavaScript to Chunks
description: Chunks input string into array based on RegExp
date: 2020-10-05 14:56:52 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a JavaScript module that chunks input string into array based on RegExp, which functions for either Web Browser or NodeJS based projects.


Check the [documentation][documentation__to_chunks] for detailed getting started and usage instructions, the [source code][source__to_chunks] is available on GitHub, and a live [demo][demo__to_chunks] is hosted by GitHub Pages.


**Example NodeJS Usage**


```javascript
const toChunks = require('to-chunks');

const input = '1.15.4-2Beta';
const regular_expression = new RegExp('\\.|-|[a-zA-Z]+');

const chunks = toChunks(input, regular_expression);

console.log(chunks);
//> ['1', '.', '15', '.', '4', '-', '2', 'Beta']
```


[documentation__to_chunks]: https://github.com/javascript-utilities/to-chunks/blob/main/.github/README.md "Repository documentation"

[source__to_chunks]: https://github.com/javascript-utilities/to-chunks "Repository source code"

[demo__to_chunks]: https://javascript-utilities.github.io/to-chunks/index.html "Live demonstration"


