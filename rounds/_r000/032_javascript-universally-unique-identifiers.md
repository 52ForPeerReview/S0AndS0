---
layout: post
title: JavaScript Universally Unique Identifiers
description: Extends `String` built-in Object to build UUID, truly unique for current scope
date: 2021-02-04 21:18:26 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---




This week I've published a JavaScript module for building Universally Unique Identifiers (UUIDs) within NodeJS or web-browser environments. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Install**


NodeJS projects may utilize `npm` to install `universally-unique-identifier` as a dependency...


```bash
cd "<your-git-project-path>"

npm install universally-unique-identifier
```


Web projects, such has those hosted on GitHub Pages, are encouraged to utilize Git Submodules instead...


```bash
cd "<your-git-project-path>"

git checkout gh-pages
mkdir -vp "assets/javascript/modules"

git submodule add -b main\
                  --name "universally-unique-identifier"\
                  "https://github.com/javascript-utilities/universally-unique-identifier.git"\
                  "assets/javascript/modules/universally-unique-identifier"
```


**Usage**


NodeJS projects can then `require` (or `import`) the classes from `universally-unique-identifier` much like any other module...


**`index.js`**


```javascript
#!/usr/bin/env node


'use strict';


const { Universally_Unique_Identifier } = require('universally-unique-identifier');


const uuid_one = new Universally_Unique_Identifier();
const uuid_two = new Universally_Unique_Identifier();


console.log(`uuid_one -> ${uuid_one}`);
//> uuid_one -> 5340a411-e6f7-4afa-8b99-d3f0f6688a5e

console.log(`uuid_two -> ${uuid_two}`);
//> uuid_two -> c271d4f0-9b47-4736-a787-7ba6c4932661

console.assert(uuid_one.toString() !== uuid_two.toString());
```


Web projects should use `script` tag(s) within HTML `head` source, and reference `universally-unique-identifier` classes within separate script file(s)...


**`index.html`**


```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Example Universally Unique Identifier</title>
    <script src="/assets/javascript/universally-unique-identifier.js" defer></script>
    <script src="/assets/javascript/index.js" defer></script>
    <style>
      #text__output {
        resize: horizontal;
        min-width: 20em;
        text-align: center;
      }
    </style>
  </head>
  <body>
    <input id="text__output" type="text" readonly>
    <br>
    <input id="button__new_uuid" type="button" value="Click for UUID">
  </body>
</html>
```


**`assets/javascript/index.js`**


```javascript
'use strict';


window.addEventListener('load', () => {
  const text__output = document.getElementById('text__output');
  const button__new_uuid = document.getElementById('button__new_uuid');

  button__new_uuid.addEventListener('click', () => {
    const uuid = new Universally_Unique_Identifier();
    text__output.value = uuid.toString();
  });
});
```



[link__documentation]: https://github.com/javascript-utilities/universally-unique-identifier/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/javascript-utilities/universally-unique-identifier "Repository source code"

