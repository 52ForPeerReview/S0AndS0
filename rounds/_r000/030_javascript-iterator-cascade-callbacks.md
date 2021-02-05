layout: post
title: JavaScript Iterator Cascade Callbacks
description: Iterator that chains callback function execution
date: 2021-01-23 20:12:34 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---


This week I've published a JavaScript module for chaining callback functions to an Iterator or Generator. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...



**Install**


NodeJS projects may utilize `npm` to install `iterator-cascade-callbacks` as a dependency...


```bash
cd "<your-git-project-path>"

npm install iterator-cascade-callbacks
```


Web projects, such has those hosted on GitHub Pages, are encouraged to utilize Git Submodules instead...


```bash
cd "<your-git-project-path>"

git checkout gh-pages
mkdir -vp "assets/javascript/modules"

git submodule add -b main\
                  --name "iterator-cascade-callbacks"\
                  "https://github.com/javascript-utilities/iterator-cascade-callbacks.git"\
                  "assets/javascript/modules/iterator-cascade-callbacks"
```


**Usage**


NodeJS projects can then `require` (or `import`) the classes from `iterator-cascade-callbacks` much like any other module...


**`index.js`**


```javascript
#!/usr/bin/env node


'use strict';


const {
  Iterator_Cascade_Callbacks,
  Stop_Iteration,
  Callback_Object,
} = require('iterator-cascade-callbacks');


/**
 * Generator that produces Fibonacci sequence
 * @see {link} https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Iterators_and_Generators
 */
function* fibonacci() {
  let current = 0;
  let next = 1;
  while (true) {
    let reset = yield current;
    [current, next] = [next, next + current];
    if (reset) {
      current = 0;
      next = 1;
    }
  }
}


const icc = new Iterator_Cascade_Callbacks(fibonacci);

const collection = icc.filter((value) => {
  return value % 2 === 0;
}).skip(1).map((evens) => {
  return evens / 2;
}).take(5).collect([]);


console.log(collection);
//> [ 1, 4, 17, 72, 305 ]
```


Web projects should use `script` tag(s) within HTML `head` source, and reference `iterator-cascade-callbacks` classes within separate script file(s)...


**`index.html`**


```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Iterator Cascade Callbacks Example</title>
  <script src="/assets/javascript/modules/iterator-cascade-callbacks/iterator-cascade-callbacks.js" defer></script>
  <script src="/assets/javascript/index.js" defer></script>
</head>
<body>
  <code>
    const counter = new Counter(<span id="code__span__counter__start">0</span>);
    <br>
    const icc = new Iterator_Cascade_Callbacks(counter);
    <br>
    <br>

    const collection = icc.filter((value) =&gt; {
    <div style="text-indent: 2em;">
      return value % <span id="code__span__filter_modulo">2</span> === 0;
    </div>
    }).map((value) =&gt; {
    <div style="text-indent: 2em;">
      return value * <span id="code__span__map_multiplier">1</span>;
    </div>
    }).take(<span id="code__span__take_amount">2</span>).collect([]);
  </code>
  <br>
  <br>

  <div id="output-text__container">
    <label for="output-text__results">Results: </label>
    <input id="output-text__results" type="text" value="" readonly>
  </div>
  <br>

  <div id="input-text__container">
    <label for="input-text__counter__start">Counter Start: </label>
    <input id="input-text__counter__start" type="text" value="0">
    <br>

    <label for="input-text__filter_modulo">Filter Modulo: </label>
    <input id="input-text__filter_modulo" type="text" value="2">
    <br>

    <label for="input-text__map_multiplier">Map Multiplier: </label>
    <input id="input-text__map_multiplier" type="text" value="1">
    <br>

    <label for="input-text__take_amount">Take Amount: </label>
    <input id="input-text__take_amount" type="text" value="2">
  </div>

  <div id="button__container">
    <input id="button__iterate" type="button" value="Iterate">
  </div>
</body>
</html>
```


**`assets/javascript/index.js`**


```javascript
'use strict';


class Counter {
  constructor(value = -1) {
    this.value = value;
    this.done = false;
  }

  next() {
    this.value++;
    return this;
  }

  [Symbol.iterator]() {
    return this;
  }
};


window.addEventListener('load', () => {
  const output_text__results = document.getElementById('output-text__results');

  const input_text__counter__start = document.getElementById('input-text__counter__start');
  const code__span__counter__start = document.getElementById('code__span__counter__start');

  const input_text__filter_modulo = document.getElementById('input-text__filter_modulo');
  const code__span__filter_modulo = document.getElementById('code__span__filter_modulo');

  const input_text__map_multiplier = document.getElementById('input-text__map_multiplier');
  const code__span__map_multiplier = document.getElementById('code__span__map_multiplier');

  const input_text__take_amount = document.getElementById('input-text__take_amount');
  const code__span__take_amount = document.getElementById('code__span__take_amount');

  const button__iterate = document.getElementById('button__iterate');
  button__iterate.addEventListener('click', () => {
    console.error('CLICKED!');
    /**
     * Parse inputs
     */
    let count_start = input_text__counter__start.value;
    if (isNaN(count_start)) {
      count_start = 0;
      input_text__counter__start = count_start;
    }
    code__span__counter__start.innerText = count_start;

    let filter_modulo = Number(input_text__filter_modulo.value);
    if (isNaN(filter_modulo)) {
      filter_modulo = 1;
      input_text__filter_modulo.value = filter_modulo;
    }
    code__span__filter_modulo.innerText = filter_modulo;

    let map_multiplier = Number(input_text__map_multiplier.value);
    if (isNaN(map_multiplier)) {
      map_multiplier = 1;
      input_text__map_multiplier.value = map_multiplier;
    }
    code__span__map_multiplier.innerText = map_multiplier;

    let take_amount = Number(input_text__take_amount.value);
    if (isNaN(take_amount)) {
      take_amount = 1;
      input_text__take_amount.value = take_amount;
    }
    code__span__take_amount.innerText = take_amount;

    const counter = new Counter(count_start);
    const icc = new Iterator_Cascade_Callbacks(counter);

    const collection = icc.filter((value) => {
      return value % filter_modulo === 0;
    }).map((value) => {
      return value * map_multiplier;
    }).take(take_amount).collect([]);

    console.log('collection ->', collection);
    const results = `[ ${collection.join(', ')} ]`;
    output_text__results.value = results;
  });
});
```



[link__documentation]: https://github.com/javascript-utilities/iterator-cascade-callbacks/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/javascript-utilities/iterator-cascade-callbacks "Repository source code"

