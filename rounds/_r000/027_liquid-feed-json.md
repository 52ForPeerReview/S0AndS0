---
layout: post
title: Liquid Feed JSON
description: JSON feed from collection and FrontMatter data
date: 2021-01-01 15:59:32 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a Liquid layout for building JSON feeds from Jekyll collections and FrontMatter data. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Clone/Install**


```bash
cd "<your-git-project-path>"


git checkout gh-pages

mkdir -vp "_layouts/modules"


git submodule add -b main\
                  --name "feed-json"\
                  "https://github.com/liquid-utilities/feed-json.git"\
                  "_layouts/modules/feed-json"
```


**Usage**

`_config.yml (snip)`


```yaml
collections_dir: documentation
collections:
  example-collection:
    output: true
    permalink: /:collection/:name/
```


---


`documentation/_example-collection/feed.json`


```yaml
layout: modules/feed-json/feed-json
title: Example Collection
collection_name: example-collection
collection_home: /example-collection/
date: 2021-01-01 11:12:13 -0700
content_type: xhtml
permalink: /:collection/:name:output_ext
```


---


`documentation/_example-collection/something-about-something.md`


```markdown
---
## Layout may be `default`, `post`, or `page` depending upon theme
layout: post

title: Title of Page
date: 2021-01-01 13:42:11 -0300
#date_updated:  ## Optional and formatted like `date` above

description: A description of page content
tags:
  - spam
  - flavored
  - ham
---


Content that expands on the topic of something about some thing
```


---


Expect JSON output similar to...


`https://<account>.github.io/<project>/example-collection/feed.json`


```json
{
  "version": "https://jsonfeed.org/version/1",
  "title": "Example Collection",
  "home_page_url": "https://<account>.github.io/<project>/",
  "feed_url": "https://<account>.github.io/<project>/example-collection/feed.json",
  "description": "A description of page content",
  "favicon": "https://<account>.github.io/favicon.ico",
  "author": {
    "name": "S0AndS0"
  },
  "expired": false
  ],
  "items": [
    {
      "id": "https://<account>.github.io/<project>/posts/<name>.<ext>",
      "url": "https://<account>.github.io/<project>/posts/<name>.<ext>",
      "title": "Title of Page",
      "content_html": "",
      "summary": "A description of page content",
      "date_published": "2021-01-01T14:13:41-14:00",
      "date_modified": "2021-01-02T14:15:00-14:00",
      "author": {
        "name": "S0AndS0"
      },
      "tags": [
        "spam",
        "flavored",
        "ham"
      ],
      "attachments": [
        {
          "url": "",
          "mime_type": "",
          "title": "",
          "size_in_bytes": 99,
          "duration_in_seconds": 42
        }
      ],
      "_custom_entry": {
        "about": "",
        "explicit": false,
        "copywrite": "AGPL-3.0",
        "owner": "",
        "subtitle": ""
      },
      "content_text": "Content that expands on the topic of something about some thing"
    }
  ]
}
```



[link__documentation]: https://github.com/liquid-utilities/feed-json/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/liquid-utilities/feed-json "Repository source code"

