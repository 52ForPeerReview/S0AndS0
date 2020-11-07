---
layout: post
title: Torrific Curl
description: Curl wrapper with Tor configuration defaults
date: 2020-11-06 17:01:05 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a Curl wrapper with Tor configuration defaults. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub.


**Clone**


```bash
mkdir -vp ~/git/hub/paranoid-linux

cd ~/git/hub/paranoid-linux

git clone --recurse-submodules git@github.com:paranoid-linux/torrific-curl.git
```


**Install**


```bash
cd ~/git/hub/paranoid-linux/torrific-curl

make install
```


**Usage**


- To download the Check Tor page...


```bash
torrific-curl 'https://check.torproject.org/' -o '/tmp/check-torproject.org.html'
```


- To send a POST request via Tor...


```bash
torrific-curl --data 'key=value' 'https://httpbin.org/post'
```


- To send a GET request over Tor...


```bash
torrific-curl -X GET\
              -H 'Accept: application/json'\
              -H 'Content-Type: application/json'\
              'https://httpbin.org/get'
```



[link__documentation]: https://github.com/paranoid-linux/torrific-curl/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/paranoid-linux/torrific-curl "Repository source code"


