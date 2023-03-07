# eslint-deno
minimal deno + eslint checking showing quirks

## this demonstrates a few issues:
- `import/no-unresolved` always unhappy
- `TypeError: cb is not a function` (12 times here, more with more files)
- always `exit`s 0 status


```sh
deno cache  npm:eslint-config-airbnb-base
deno run -A npm:eslint .


./app.js
  1:8  error  Unable to resolve path to module './lib.js'           import/no-unresolved
  1:8  error  Unexpected use of file extension "js" for "./lib.js"  import/extensions

✖ 2 problems (2 errors, 0 warnings)


Oops! Something went wrong! :(

ESLint: 8.35.0

TypeError: cb is not a function
    at file:///Users/tracey/dev/eslint-deno/node_modules/.deno/resolve@1.22.1/node_modules/resolve/lib/async.js:169:17
    at load (file:///Users/tracey/dev/eslint-deno/node_modules/.deno/resolve@1.22.1/node_modules/resolve/lib/async.js:186:43)
    at onex (file:///Users/tracey/dev/eslint-deno/node_modules/.deno/resolve@1.22.1/node_modules/resolve/lib/async.js:211:17)
    at file:///Users/tracey/dev/eslint-deno/node_modules/.deno/resolve@1.22.1/node_modules/resolve/lib/async.js:24:69
    at internal:deno_node/polyfills/_fs/_fs_stat.ts:83:88

Oops! Something went wrong! :(

ESLint: 8.35.0

TypeError: cb is not a function
    at file:///Users/tracey/dev/eslint-deno/node_modules/.deno/resolve@1.22.1/node_modules/resolve/lib/async.js:169:17
    at load (file:///Users/tracey/dev/eslint-deno/node_modules/.deno/resolve@1.22.1/node_modules/resolve/lib/async.js:186:43)
    at onex (file:///Users/tracey/dev/eslint-deno/node_modules/.deno/resolve@1.22.1/node_modules/resolve/lib/async.js:211:17)
    at file:///Users/tracey/dev/eslint-deno/node_modules/.deno/resolve@1.22.1/node_modules/resolve/lib/async.js:24:69
    at internal:deno_node/polyfills/_fs/_fs_stat.ts:83:88

Oops! Something went wrong! :(

...
```
