---
layout: post
title: API List Path
description: ExpressJS example app that lists server-side path
date: 2020-11-19 16:42:00 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



I've published an example web API built with ExpressJS. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub; the TLDR (quick-start) is as follows...


**Clone**


```bash
mkdir -vp ~/git/hub/web-dev-examples

cd ~/git/hub/web-dev-examples

git clone git@github.com:web-dev-examples/api-list-path
```


**Install Dependencies**


```bash
cd ~/git/hub/web-dev-examples/api-list-path

npm install
```


**Usage**


Start the server via NPM run target...


```bash
npm run start
```


With a web-browser navigate to `http://localhost:8080` for example front-end interaction.


Or use Curl to send HTTP POST requests...


```bash
curl --data 'path=.' --url 'http://localhost:8080/list'
```



[link__documentation]: https://github.com/web-dev-examples/api-list-path/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/web-dev-examples/api-list-path "Repository source code"

