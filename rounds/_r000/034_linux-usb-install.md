---
layout: post
title: Linux USB Install
description: Blog style post about writing the guide
date: 2021-02-18 12:24:52 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a detailed guide for installing Linux to a USB drive, compatible with UEIF boot, all with minimal changes to the host environment. The full tutorial is hosted on GitHub pages [`https://install-linux-guides.github.io/usb-uefi-compatible/`][link__guide], the source code and content that builds the tutorial is available for cloning too [`install-linux-guides/usb-uefi-compatible`][link__source], and this post will be a bit _meta_ in that I'll be writing about how I wrote the guide.


This project required that I learn much more about publishing web content in a fashion that is respectful of device/network limitations. After learning about how to utilize [HTML `picture` element][link__html_picture_element] for allowing web-browsers a choice of image source, I researched tools for [Linux image conversion][link__linux_image_conversion], then because I had organized pages and images with number prefixes, eg...


```
_virtual-box/00-create-virtual-machine.md
_virtual-box/01-virtual-machine-storage.md
```


... which was unnecessary thanks to [Jekyll Collection Ordering][link__jekyll__collection__manually_ordering_documents], I learned about configuring [Ranger][link__linux_ranger_text_editor] for bulk renaming via Vim buffers.


Next week I'll likely pick a slightly easier project to publish so that a bit more time can be dedicated to polishing the tutorial navigation and instructions.



[link__source]: https://github.com/install-linux-guides/usb-uefi-compatible/

[link__guide]: https://install-linux-guides.github.io/usb-uefi-compatible/

[link__linux_image_conversion]: https://s0ands0.github.io/100-days-of-code/r001/040-linux-image-conversion/

[link__html_picture_element]: https://s0ands0.github.io/100-days-of-code/r001/041-html-picture-element/

[link__linux_ranger_text_editor]: https://s0ands0.github.io/100-days-of-code/r001/045-linux-ranger-text-editor/

[link__jekyll__collection__manually_ordering_documents]: https://jekyllrb.com/docs/collections/#manually-ordering-documents

