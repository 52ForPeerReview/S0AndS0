---
layout: post
title: To Do PWA
description: Static web-app that utilizes modern CSS, HTML, and JavaScript
date: 2021-05-09 17:41:30 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a static PWA (Progressive Web App) that utilizes modern CSS, HTML, and JavaScript; all without any server-side databases or scripting. Check the [live demo][link__web_site] to explore the features, and the [documentation][link__documentation] for how to submit bug reports or suggest enhancements; source code is, as always, available via [GitHub][link__source].


Git may be used to clone source code and edit locally, eg...


```Bash
mkdir -vp ~/git/hub/web-dev-examples

cd ~/git/hub/web-dev-examples

git clone --recurse-submodules git@github.com:web-dev-examples/to-do-app.git
```


Development decencies are tracked via NPM so must be installed for testing/development...


```bash
cd ~/git/hub/web-dev-examples/to-do-app

npm install
```


Nearly any web-server may be used to host static web assets...


```bash
npm run py-serve
```



[link__documentation]: https://github.com/web-dev-examples/to-do-app/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/web-dev-examples/to-do-app "Repository source code"

[link__web_site]: https://web-dev-examples.github.io/to-do-app/index.html

