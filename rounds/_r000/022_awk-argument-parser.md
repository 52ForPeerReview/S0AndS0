---
layout: post
title: Awk Argument Parser
description: Including within Awk script adds argument parsing functionality
date: 2020-11-24 17:09:25 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a function for argument parsing within Awk scripts. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub; the TLDR (quick-start) is as follows...


**Clone**


```bash
cd /usr/local/etc

sudo git clone https://github.com/awk-utilities/includes-argument-parser.git
```


**Install**


```bash
cd /usr/local/etc/includes-argument-parser

sudo make install
```


**`include-installed.awk`**


```awk
#!/usr/bin/gawk -f


## For updates see -> https://github.com/awk-utilities/includes-argument-parser
@include "argument-parser"


BEGIN {
  delete parsed_arguments
  delete acceptable_arguments

  acceptable_arguments["string"] = "--string|-s:value"
  acceptable_arguments["boolean"] = "--boolean|-B:bool"
  acceptable_arguments["usage"] = "--usage:bool"
  acceptable_arguments["increment"] = "--increment|-I:increment"
  acceptable_arguments["array"] = "--array:array"

  argument_parser(acceptable_arguments, parsed_arguments)
  for (k in parsed_arguments) {
    if (k == "array") {
      for (i in parsed_arguments[k]) {
        print "parsed_arguments[\"" k "\"][" i "] ->", parsed_arguments[k][i]
      }
    } else {
      print "parsed_arguments[\"" k "\"] ->", parsed_arguments[k]
    }
  }
}
```


Provide executable permissions...


```bash
chmod u+x include-installed.awk
```


Then run the Awk script...


```bash
./include-installed.awk -t 'string like value' -f --increment -I -I
#> parsed_arguments["flag"] -> 1
#> parsed_arguments["increment"] -> 3
#> parsed_arguments["test"] -> string like value
```



[link__documentation]: https://github.com/awk-utilities/includes-argument-parser/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/awk-utilities/includes-argument-parser "Repository source code"

