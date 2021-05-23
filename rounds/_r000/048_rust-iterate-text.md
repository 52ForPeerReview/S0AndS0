---
layout: post
title: Rust Iterate Text
description: Library of helper functions and structures for iterating over text and files
date: 2021-05-23 14:44:13 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a Rust library of helper functions and structures for iterating over text and files. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**`Cargo.toml` (snip)**


```toml
[dependencies]
iterate-text = "0.0.1"
```


**`src/main.rs` (example)**


```rust
#!/usr/bin/env rust


use iterate_text::file::lines::IterateFileLines;


fn main() {
    let mut iter = IterateFileLines::new("tests/file/lines/file.txt");

    assert_eq!(iter.next(), Some("First line\n"));
    assert_eq!(iter.next(), Some("Second line\n"));
    assert_eq!(iter.next(), Some("Third line\n"));
    assert_eq!(iter.next(), None);
}

```


---


Application examples may be run by cloning the repository from GitHub


**Clone**


```bash
mkdir -vp ~/git/hub/rust-utilities

cd ~/git/hub/rust-utilities

git clone git@github.com:rust-utilities/iterate-text.git
```


**`examples/version-compare.rs`**


```bash
cargo run --example file-reader -- --file .github/README.md -c 10
```



[link__documentation]: https://github.com/rust-utilities/iterate-text/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/rust-utilities/iterate-text "Repository source code"

