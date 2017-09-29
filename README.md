# sample-es6-library

This shows how to distribute an ES6 library
using [Babel](https://babeljs.io/)
and [rollup](https://rollupjs.org/).

- `package.json#module` points to the raw ES6 code for modern browser
  consumption
- `package.json#main` points to legacy browser/node support and
  CommonJS modules. 

Under the hood, it uses Babel
and
[babel-runtime](https://babeljs.io/docs/plugins/transform-runtime/)
for legacy browser/Node.js support. babel-runtime (actually the
transform-runtime plugin) polyfills only what the library uses and
does so in a way that doesn't conflict with other versions of
Babel. This is perfect for libraries.

We use rollup only to create the UMD bundle for JSFiddle consumption.

## Building

``` bash
npm run build
// then publish to npm...
```

## Installation

``` bash
npm install sample-es6-library // from an app
```

## Consumption

``` javascript
// Web, webpack consumption, modern browsers only
import foo from 'sample-es6-library'
// Web, webpack consumption, legacy browser support
import foo from 'sample-es6-library/dist/legacy/index'
// Node.js
const foo = require('sample-es6-library')
```

JSFiddle support: `dist/legacy-umd/index.js` is a UMD bundle that can
be put behind a CDN and loaded via a `<script>` tag. For
example,
[here it is via jsdeliver.com](https://cdn.jsdelivr.net/npm/sample-es6-library@0.0.2/dist/legacy-umd/index.min.js),
and [here it is in a fiddle](https://jsfiddle.net/droux38f/1/).

