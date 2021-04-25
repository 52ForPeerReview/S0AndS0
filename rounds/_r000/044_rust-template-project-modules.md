---
layout: post
title: Rust Template Project Modules
description: Template that provides examples of using project modules
date: 2021-04-25 11:29:00 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a Rust template for demonstrating project module usage. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Install Dependencies**


```bash
cargo install cargo-generate
```


**Initialize a Project from Repository**


```bash
cargo generate --name 'your-application-name'\
               --git https://github.com/rust-utilities/template-project-modules.git
```


Or configure as a named template...


_`$CARGO_HOME/cargo-generate`_


```Conf
[favorite.project-modules]
description = "Template for application scoped modules"
git = "https://github.com/rust-utilities/template-project-modules.git"
branch = "main"
```


... and initialize a project via favorite name...


```bash
cargo generate project-modules your-application-name
```


**Build and Customize**


```bash
cd your-application-name

cargo run

vim src/main.rs
```


There are examples within the source code of how to `use` modules within various scopes, as well as from directory and file level modules.



[link__documentation]: https://github.com/rust-utilities/template-project-modules/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/rust-utilities/template-project-modules "Repository source code"

