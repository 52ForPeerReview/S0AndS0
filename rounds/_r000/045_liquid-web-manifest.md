---
layout: post
title: Liquid Web Manifest
description: Build `webmanifest` file from FrontMatter or YAML
date: 2021-05-03 16:30:39 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a Liquid layout for building `webmanifest` files from FrontMatter or YAML configurations.  Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Clone/Install**


```bash
cd <your-project>


mkdir -p _layouts/modules


git submodule add -b main\
                  --name webmanifest\
                  'https://github.com/liquid-utilities/webmanifest.git'\
                  '_includes/modules/webmanifest'
```


Write a web manifest file within your project...


**`site.webmanifest`**


```YAML
---
layout: modules/webmanifest/webmanifest

name: Liquid Utilities -- Site Web Manifest Example
short_name: Site Web Manifest Example

icons:
  filter: relative_url

  - src: assets/images/icons/android-chrome-192x192.png
    purpose: monochrome

    sizes: 192x192
    type: image/png

  - src: assets/images/icons/android-chrome-384x384.png
    filter: absolute_url
    type: image/png
---
```


... and expect JSON formatted results similar to the following after building...


```JSON
{
    "name": "Liquid Utilities -- Site Web Manifest Example",
    "short_name": "Site Web Manifest Example",
    "icons": [
        {
            "src": "/webmanifest/assets/images/icons/android-chrome-192x192.png",
            "sizes": "192x192",
            "type": "image/png"
        },
        {
            "src": "https://liquid-utilities.github.io/webmanifest/assets/images/icons/android-chrome-384x384.png",
            "sizes": "384x384",
            "type": "image/png"
        }
    ],
    "theme_color": "#ffffff",
    "background_color": "#ffffff",
    "display": "standalone"
}
```


[link__documentation]: https://github.com/liquid-utilities/webmanifest/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/liquid-utilities/webmanifest "Repository source code"

[link__tweet]: https://twitter.com/S0_And_S0/status/1389369978412019715

