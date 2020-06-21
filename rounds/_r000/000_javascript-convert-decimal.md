---
layout: post
title: JavaScript convert decimal
description: Converts decimal to another base, eg. hex, octal, or binary
date: 2020-06-21 14:12:58 -0700
# date_updated:  ## Optional, formatted like Sat Jun 20 15:00:58 PDT 2020 above
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
