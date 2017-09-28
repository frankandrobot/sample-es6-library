# sample-es6-library

This shows how to distribute an ES6 library.

- `package.json#module` points to the raw ES6 code for modern browser
  consumption
- `package.json#main` points to legacy browser/node support and
  CommonJS modules. 
  
Consumption:

``` javascript
// Web, webpack consumption, modern browsers only
import foo from 'sample-es6-library'
// Web, webpack consumption, legacy browser support
import foo from 'sample-es6-library/dist/legacy/index'
// Node.js
const foo = require('sample-es6-library')
```
