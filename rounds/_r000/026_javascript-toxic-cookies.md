---
layout: post
title: JavaScript Toxic Cookies
description: Tool for poisoning browser cookies of currently loaded domain
date: 2020-12-24 18:25:35 -0800
# date_updated:  ## Optional, formatted like 'date' above
time_to_live: 1800
---



This week I've published a tool for poisoning browser cookies of currently loaded domain. Check the [documentation][link__documentation] for detailed getting started and usage instructions, the [source code][link__source] is available on GitHub. What follows is the TLDR for installation and usage...


**Clone/Install**


```bash
cd "<your-git-project-path>"

mkdir -vp assets/javascript/modules

git submodule add -b main\
                  --name toxic-cookies\
                  https://github.com/javascript-utilities/toxic-cookies.git\
                  assets/javascript/modules/toxic-cookies
```


**Usage**


`index.html`


```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8">
    <title>Toxic Cookies Tests</title>
    <script src="assets/javascript/toxic-cookies/toxic-cookies.js" differ></script>
    <script src="assets/javascript/index.js" differ></script>
  </head>

  <body>
    <div id="container__inputs">
      <input type="button"
             id="button__poison_cookies"
             for="button__print_cookies"
             value="Poison Cookies">

      <input type="button"
             id="button__print_cookies"
             for="container__cookie_output"
             value="Print Cookies">

      <input type="button"
             id="button__empty_cookies"
             for="button__print_cookies"
             value="Empty Cookies">

      <input type="button"
             id="button__refresh"
             value="Refresh">
    </div>

    <div id="container__outputs">
      <pre id="container__cookie_output"></pre>
    </div>
  </body>
</html>
```


`assets/javascript/index.js`


```javascript
'use strict';


const toxic_cookies = new Toxic_Cookies({
  clean_keys: ['auth'],
  max_bite_size: 4090,
  path: document.location.pathname,
  key_callback: () => { return Math.random(); },
  value_callback: () => { return Math.random(); },
});


window.addEventListener('load', () => {
  const button__poison_cookies = document.getElementById('button__poison_cookies');
  button__poison_cookies.addEventListener('click', (event) => {
    toxic_cookies.poisionAllCookies();

    const button__print_cookies__id = event.target.getAttribute('for');
    const button__print_cookies = document.getElementById(button__print_cookies__id);
    button__print_cookies.click();
  });

  const button__print_cookies = document.getElementById('button__print_cookies');
  button__print_cookies.addEventListener('click', (event) => {
    const objectified_cookies = toxic_cookies.constructor.objectifyCookies();
    const output_id = event.target.getAttribute('for');
    const container__cookie_output = document.getElementById(output_id);
    container__cookie_output.innerText = JSON.stringify(objectified_cookies, null, 2);
  });

  const button__empty_cookies = document.getElementById('button__empty_cookies');
  button__empty_cookies.addEventListener('click', (event) => {
    const experation = toxic_cookies.constructor.calculateCookieExpiration(-1);
    const cookie_metadata = `expires=${experation};path=${toxic_cookies.path}`;

    const objectified_cookies = toxic_cookies.constructor.objectifyCookies();
    Object.entries(objectified_cookies).forEach(([key, value]) => {
      if (!toxic_cookies.clean_keys.includes(key)) {
        window.document.cookie = `${key}=;${cookie_metadata}`;
      }
    });

    const button__print_cookies__id = event.target.getAttribute('for');
    const button__print_cookies = document.getElementById(button__print_cookies__id);
    button__print_cookies.click()
  });

  const button__refresh = document.getElementById('button__refresh');
  button__refresh.addEventListener('click', (_event) => {
    window.location.reload(false);
    return false;
  });

  button__print_cookies.click();
});
```


[link__documentation]: https://github.com/javascript-utilities/toxic-cookies/blob/main/.github/README.md "Repository documentation"

[link__source]: https://github.com/javascript-utilities/toxic-cookies "Repository source code"

