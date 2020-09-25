---
layout: post
title: JavaScript Objectify Cookies
description: Builds dictionary/object from browser cookies string
date: 2020-09-23 15:02:05 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I have published a JavaScript module for converting Browser cookies to an Object/Dictionary.


Check the [documentation][documentation__objectify_cookies] for detailed getting started and usage instructions, the [source code][source__objectify_cookies] is available on GitHub, and a live [demo][demo__objectify_cookies] is hosted by GitHub Pages.


**Example Usage**


```javascript
const cookies = objectifyCookies(true);
console.log(cookies['key_name']);
```


[documentation__objectify_cookies]: https://github.com/javascript-utilities/objectify-cookies/blob/main/.github/README.md "Repository documentation"

[source__objectify_cookies]: https://github.com/javascript-utilities/objectify-cookies "Repository source code"

[demo__objectify_cookies]: https://javascript-utilities.github.io/objectify-cookies/index.html

