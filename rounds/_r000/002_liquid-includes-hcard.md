---
layout: post
title: Liquid Includes HCard
description: Builds HCard compatible with VCard HTML format
date: 2020-06-29 17:55:12 -0700
# date_updated: 2020-07-05 12:55:12 -0700
time_to_live: 1800
---



This week I'll be working on publishing a Liquid module for building HCard/VCard formatted HTML. Push date is tentatively scheduled for Tuesday 2020-07-07


## Update
[heading__update]: #update "Updates about publishing project"


{% assign date_format = site[site.theme].date_format | default: "%b %-d, %Y" %}

As of {{ page.date_updated | date: date_format }} this project is now live!


Check the [documentation][documentation__includes_hcard] for detailed getting started and usage instructions, a [live demo][demo__includes_hcard] is hosted thanks to GitHub Pages, and the [source code][source__includes_hcard] is available on GitHub.



[documentation__includes_hcard]: https://github.com/liquid-utilities/includes-hcard/blob/main/.github/README.md "Repository documentation"

[source__includes_hcard]: https://github.com/liquid-utilities/includes-hcard "Repository source code"

[demo__includes_hcard]: https://liquid-utilities.github.io/includes-hcard/

[question__code_review__stack_exchange]: https://codereview.stackexchange.com/questions/245100/liquid-includes-hcard-module
