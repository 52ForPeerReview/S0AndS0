---
layout: post
title: Liquid Includes Picture
description: Builds `picture` element from FrontMatter and includes
date: 2021-03-24 12:08:07 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a Liquid project for building HTML picture element from FrontMatter and includes. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...



**Clone/Install**


```bash
cd <your-project>


mkdir -p _includes/modules


git submodule add -b main\
                  --name includes-picture\
                  'https://github.com/liquid-utilities/includes-picture.git'\
                  '_includes/modules/includes-picture'
```


**Usage**


Define page or layout FrontMatter similar to...


```yaml
pictures:
  funny_cat:
    url:
      base: assets/images/funny-cat/
      filter: relative_url

    img:
      alt: Picture of a funny cat playing with yarn ball
      src: playful-yarn.jpeg
      width: 300
      height: 200
      loading: lazy
      decoding: async

    sources:
      - srcset: playful-yarn.png

      - srcset:
        - playful-yarn-480.webp
        - playful-yarn-480-2x.webp 2x
        media: '(min-width: 600px)'
```


> Check the [API][link__documentation__api] section for details on types, and structure, of data for the `pictures` _name-space_


Include named picture data within a layout, page, and or post file...


{% raw %}
```liquid
{% include modules/includes-picture/picture.html name='funny_cat' %}
```
{% endraw %}


HTML similar to the following will be generated...


```html
<picture>
  <source type="image/png"
          srcset="/includes-picture/assets/images/funny-cat/playful-yarn.png"
  />

  <source type="image/webp"
          srcset="/includes-picture/assets/images/funny-cat/playful-yarn-480.webp,
                  /includes-picture/assets/images/funny-cat/playful-yarn-480-2x.webp 2x"
          media="(min-width: 600px)"
  />

  <img src="/includes-picture/assets/images/funny-cat/playful-yarn.jpeg"
       height="300"
       width="200"
       alt="Picture of a funny cat playing with yarn ball"
       loading="lazy"
       decoding="async"
  />
</picture>
```


> Note, provided that your site is configured properly the _`/includes-picture/`_ portion of above _`src`_, and _`srcset`_, paths will be replaced automagically with the name of your repository.



[link__documentation]: https://github.com/liquid-utilities/includes-picture/blob/main/.github/README.md "Repository documentation"

[link__documentation__api]: https://github.com/liquid-utilities/includes-picture/blob/main/.github/README.md#api "Repository API documentation"

[link__source]: https://github.com/liquid-utilities/includes-picture "Repository source code"

