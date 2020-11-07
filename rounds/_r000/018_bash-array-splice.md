---
layout: post
title: Bash Array Splice
description: Removes elements from Bash array
date: 2020-10-30 12:55:41 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a Bash submodule that removes elements from Bash array. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub.


**Bash Variables**


```Bash
_module_name='array-splice'
_module_https_url="https://github.com/bash-utilities/array-splice.git"
_module_base_dir='modules'
_module_path="${_module_base_dir}/${_module_name}"
```


**Bash Submodule Commands**


```Bash
cd "<your-git-project-path>"

mkdir -vp "${_module_base_dir}"

git submodule add --name "${_module_name}"\
                  -b main\
                  "${_module_https_url}"\
                  "${_module_path}"
```


Write a script that makes use of `array_splice` function...


```Bash
#!/usr/bin/env bash


## Find directory that this script resides in
__SOURCE__="${BASH_SOURCE[0]}"
while [[ -h "${__SOURCE__}" ]]; do
    __SOURCE__="$(find "${__SOURCE__}" -type l -ls | sed -n 's@^.* -> \(.*\)@\1@p')"
done
__DIR__="$(cd -P "$(dirname "${__SOURCE__}")" && pwd)"


## Provides array_splice '<list_ref>' '<item>' '<offset>'
source "${__DIR__}/modules/array-splice/array-splice.sh"


list=(
    --beginning 'foo'
    --middle 'bar'
    --end 'spam'
)

printf '${list[*]} -> ( %s )\n' "${list[*]}"

echo "#> array_splice --target 'list' --element '--middle' --offset 1"
array_splice --target 'list' --element '--middle' --offset 1

printf '${list[*]} -> ( %s )\n' "${list[*]}"
## Expected output
#> ${list[*]} -> ( --beginning foo --end spam )
```



[link__documentation]: https://github.com/bash-utilities/array-splice/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/bash-utilities/array-splice "Repository source code"

