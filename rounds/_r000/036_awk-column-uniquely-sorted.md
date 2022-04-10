---
layout: post
title: Awk Column Uniquely Sorted
description: Script for sorting unique columns from a list of files
date: 2021-03-03 11:40:16 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published an Awk script for sorting unique columns from a list of files. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


## Quick Start
[heading__quick_start]: #quick-start


**Clone**


```Bash
mkdir -vp ~/git/hub/awk-utilities

cd ~/git/hub/awk-utilities

git clone git@github.com:awk-utilities/column-uniquely-sorted.git
```


**Install**


Project script(s) and manual page(s) may be installed via `make install` command...


```Bash
cd ~/git/hub/awk-utilities/column-uniquely-sorted

make install
```


**Uninstall**


Script(s) and manual page(s) for this project may be uninstalled via `uninstall` Make target...


```Bash
cd ~/git/hub/awk-utilities/column-uniquely-sorted

make uninstall
```


**Upgrade**


To update in the future use `make upgrade` command...


```Bash
cd ~/git/hub/awk-utilities/column-uniquely-sorted

make upgrade
```


**Documentation**


After installation documentation may be accessed via `man` command, eg...


```Vim
man column-uniquely-sorted.awk
```


______


## Example Usage
[heading__example_usage]: #example-usage


**`file-one.txt`**


```
foo
bar
spam
ham
```


**`file-two.txt`**


```
foo
lamb
spam
ham
```


By default the `column-uniquely-sorted.awk` script will sort unique lines, not just an individual column...


```
column-uniquely-sorted.awk file-one.txt file-two.txt
#> bar
#> foo
#> ham
#> lamb
#> spam
```


And it is possible to instead sort by count, as well as reverse sort order...


```
column-uniquely-sorted.awk --count\"
                           --reverse\" 
                           file-one.txt\
                           file-two.txt
#> 2 spam
#> 2 ham
#> 2 foo
#> 1 lamb
#> 1 bar
```



[link__documentation]: https://github.com/awk-utilities/column-uniquely-sorted/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/awk-utilities/column-uniquely-sorted "Repository source code"

[link__tweet]: https://twitter.com/S0_And_S0/status/1367200728020905986

