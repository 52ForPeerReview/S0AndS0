---
layout: post
title: Shellchecker
description: Shebang wrapper that runs script if `shellcheck` returns no errors
date: 2020-10-14 16:21:47 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I have published a Shebang wrapper that runs script if `shellcheck` returns no errors.


Check the [documentation][documentation__shellchecker] for detailed getting started and usage instructions, the [source code][source__shellchecker] is available on GitHub.


After installation, write a script that uses `/usr/local/sbin/shellchecker` as the shebang...


**`example.sh`**


```Bash
#!/usr/local/sbin/shellchecker --format=gcc bash --restricted

_argument_list=("${@}")
for i in "${!_argument_list[@]}"; do
    printf '_argument_list[%i] -> %s\n' "${i}" "${_argument_list[${i}]}"
done
```


Provide executable permissions and run `example.sh` script...


```Bash
chmod u+x ./example.sh


./example.sh
```



[documentation__shellchecker]: https://github.com/vim-utilities/shellchecker/blob/main/.github/README.md "Repository documentation"

[source__shellchecker]: https://github.com/paranoid-linux/shellchecker "Repository source code"

