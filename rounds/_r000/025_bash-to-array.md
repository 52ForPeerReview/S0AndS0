---
layout: post
title: Bash to Array
description: Bash array from string with quote parsing
date: 2020-12-17 12:29:33 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a submodule for converting strings to Bash arrays. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Clone/Install**


```bash
cd "<your-git-project-path>"

mkdir modules

git submodule add -b main\
                  --name to-array\
                  https://github.com/bash-utilities/to-array.git\
                  modules/to-array
```


**Usage**


```bash
#!/usr/bin/env bash


__SOURCE__="${BASH_SOURCE[0]}"
while [[ -h "${__SOURCE__}" ]]; do
    __SOURCE__="$(find "${__SOURCE__}" -type l -ls | sed -n 's@^.* -> \(.*\)@\1@p')"
done
__DIR__="$(cd -P "$(dirname "${__SOURCE__}")" && pwd)"


## Provides to_array -t '<array_reference>' -i '<string>'
source "${__DIR__}/modules/to-array/to-array.sh"


__usage__() {
    cat <<EOF
Converts list of arguments to array(s) and prints results
EOF
}


_arguments=( "${@}" )
for _index in "${!_arguments[@]}"; do
    _argument="${_arguments[${_index}]}"
    case "${_argument}" in
        -h|--help)
            __usage__
            exit 0
        ;;
        *)
            target=()
            to_array -t 'target' -i "${_argument}" --strip-quotes
            printf '_argument[%i] -> ( %s )\n' "${_index}" "${target[*]@Q}"
        ;;
    esac
done
```


Provide executable permissions and run `example.sh` script...


```bash
chmod u+x example.sh

./example.sh '"spam flavored" ham "in a can"'
#> _argument[0] -> ( 'spam flavored' 'ham' 'in a can' )
```



[link__documentation]: https://github.com/bash-utilities/to-array/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/bash-utilities/to-array "Repository source code"

