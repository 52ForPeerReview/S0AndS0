---
layout: post
title: Liquid Includes Font
description: Jekyll plugin for loading fonts in a respectful fashion
date: 2021-04-06 12:21:53 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a Liquid project for loading web-fonts in a respectful fashion. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


______


**Clone/Install**


```bash
cd <your-project>


mkdir -p _includes/modules


git submodule add -b main\
                  --name includes-font\
                  'https://github.com/liquid-utilities/includes-font.git'\
                  '_includes/modules/includes-font'
```


______


**Usage**


Example YAML/FrontMatter


```yaml
fonts_list:
  - href: assets/fonts/custom-font.css
    preconnect: /
    filter: relative_url

  - href: https://fonts.googleapis.com/css2?family=Merriweather&display=swap
    preconnect: https://fonts.gstatic.com
```


---


Example Layout


**`page.html` (snip)**


```liquid
<!DOCTYPE html>
<html lang="en">
  <head>
    {% assign fonts_list = page.fonts_list
                         | default: site.fonts_list
                         | default: layout.fonts_list %}

    {%- for font in fonts_list -%}
      {% include _includes/modules/include-font/font.html
                 href=font.href
                 preconnect=font.preconnect
                 filter=font.filter %}
    {%- endfor -%}
  </head>
</html>
```


---


Example Output


```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="preconnect"
          href="/project-name"/>

    <link rel="preload"
          as="style"
          href="/project-name/assets/fonts/custom-font.css"/>

    <link rel="stylesheet"
          href="/project-name/assets/fonts/custom-font.css"
          media="print"
          onload="this.media='all'"/>

    <noscript>
      <link rel="stylesheet"
            href="/project-name/assets/fonts/custom-font.css"/>
    </noscript>


    <link rel="preconnect"
          href="https://fonts.gstatic.com"
          crossorigin/>

    <link rel="preload"
          as="style"
          href="https://fonts.googleapis.com/css2?family=Merriweather&display=swap"/>

    <link rel="stylesheet"
          href="https://fonts.googleapis.com/css2?family=Merriweather&display=swap"
          media="print"
          onload="this.media='all'"/>

    <noscript>
      <link rel="stylesheet"
            href="https://fonts.googleapis.com/css2?family=Merriweather&display=swap"/>
    </noscript>
  </head>
</html>
```


> Note, provided that your site is configured properly the _`/project-name/`_ portion of above _`href`_ paths will be replaced automagically with the name of your repository.



[link__documentation]: https://github.com/liquid-utilities/includes-font/blob/main/.github/README.md "Repository documentation"

[link__documentation__api]: https://github.com/liquid-utilities/includes-font/blob/main/.github/README.md#api "Repository API documentation"

[link__source]: https://github.com/liquid-utilities/includes-font "Repository source code"

