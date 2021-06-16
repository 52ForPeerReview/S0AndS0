---
layout: post
title: Rust Color Operators
description: Library of color data structures, converters, comparators, and arithmetic operators
date: 2021-06-16 15:03:02 -0700
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a Rust library of color data structures, converters, comparators, and arithmetic operators. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**`Cargo.toml` (snip)**


```toml
[dependencies]
color-operators = "0.0.1"
```


**`src/main.rs` (example)**


```rust
extern crate color_operators;

use color_operators::color::Color;
use color_operators::hsl::HSL;
use color_operators::hsv::HSV;
use color_operators::rgb::RGB;


fn main() {
    let c = Color::new_rgb(255, 42, 90);
    assert_eq!(c, RGB::new(255, 42, 90));

    let hsv: HSV = c.clone().into():
    let hsl: HSL = c.clone().into():

    assert_eq!(hsv, hsl);
}
```


---


Application examples may be run by cloning the repository from GitHub


**Clone**


```bash
mkdir -vp ~/git/hub/rust-utilities

cd ~/git/hub/rust-utilities

git clone git@github.com:rust-utilities/color-operators.git

cd color-operators
```


Code within the `examples/` directory may be run via _`cargo run --example <name> -- <arguments>`_


```bash
cargo run --example rgb-to-hsl -- -r 255
#> HSL { hue: 0.0, saturation: 1.0, lightness: 0.5 }

cargo run --example rgb-to-hsv -- -g 255
#> HSV { hue: 120.0, saturation: 1.0, value: 1.0 }
```


[link__documentation]: https://github.com/rust-utilities/color-operators/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/rust-utilities/color-operators "Repository source code"

