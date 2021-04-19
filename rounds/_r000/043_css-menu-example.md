---
layout: post
title: CSS Menu Example
description: Pure CSS and HTML navigation menu example
date: 2021-04-19 16:05:21 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published an example navigation menu that is built with pure CSS and HTML. Check the [live demo][link__web_site] to explore the features, and the [documentation][link__documentation] for how to submit bug reports or suggest enhancements; source code is, as always, available via [GitHub][link__source].


Git may be used to clone source code and edit localy, eg...


```Bash
mkdir -vp ~/git/hub/web-dev-examples

cd ~/git/hub/web-dev-examples

git clone git@github.com:web-dev-examples/css-navigation-menu.git
```


... after which there are only two files of interest:


- **`index.html`** contains HTML5 elements that define page structure, and inline CSS3 is leveraged to provide core menu functionality.


- **`assets/css/style.css`** provides additional styling and further enhances menu presentation.


Python or your faviourit development web-server may be used to test site and any changes, eg...


```bash
cd ~/git/hub/web-dev-examples/css-navigation-menu

python3 -m http.server --bind 127.0.0.1 8080
```


[link__documentation]: https://github.com/web-dev-examples/css-navigation-menu/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/web-dev-examples/css-navigation-menu "Repository source code"

[link__web_site]: https://web-dev-examples.github.io/css-navigation-menu/index.html

