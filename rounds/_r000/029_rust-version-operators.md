---
layout: post
title: Rust Version Operators
description: Rust library for comparing and manipulating version numbers
date: 2021-01-15 16:39:26 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a Rust library for comparing, adding, and subtracting version-like inputs. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**`Cargo.toml` (snip)**


```toml
[dependencies]
version_operators = "0.0.1"
```


**`src/main.rs` (example)**


```rust
use version_operators::Version;

fn main() {
    let version = Version::from_str("1.14.3");

    let expected = vec![1, 14, 3];

    assert_eq!(version.to_vector(), expected);
}
```


---


Application examples may be run by cloning the repository from GitHub


**Clone**


```bash
mkdir -vp ~/git/hub/rust-utilities

cd ~/git/hub/rust-utilities

git clone git@github.com:rust-utilities/version_operators.git
```


**`examples/version-compare.rs`**


```bash
cargo run --example version-compare '1.14.3' '-lt' '1.14.4'
#> true

cargo run --example version-compare '1.14.3' '==' '1.14.4'
#> false
```


**`examples/version-math.rs`**


```bash
cargo run --example version-math '1.14.4' '-add' '1.14.3'
#> [2, 28, 7]

cargo run --example version-math '1.14.4' '-sub' '1.14.3'
#> [0, 0, 1]
```


**`examples/version-increment.rs`**


```bash
cargo run --example version-increment '1.14.3' '1'
#> [1, 15, 3]
```



[link__documentation]: https://github.com/rust-utilities/version_operators/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/rust-utilities/version_operators "Repository source code"

