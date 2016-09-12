# redux-api-simple-middleware
[![NPM version][npm-image]][npm-url] [![Downloads][downloads-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Dependency status][david-dm-image]][david-dm-url]
---
A simple and useful solution to control the network activities of your Redux app;

It is based on Redux,so I didn't write that in `package.json`

## Simple use with this middleware

run `npm install redux-api-simple-middleware --save` in your project first

import it in your `configStore.js` file(the file that you create a store and add other middleware) with:
`import api-middleware from 'redux-api-simple-middleware'`

then ...(still working on it)

```

{
  "name": "redux-api-simple-middleware",
  "version": "1.0.0",
  "description": "This is a simple and useful middleware for redux without much learn",
  "main": "index.js",
  "scripts": {
    "test": "make test"
  },
  "repository": {
    "type": "git",
    "url": "https://github.com/879479119/redux-api-simple-middleware"
  },
  "keywords": [
    "redux",
    "easy",
    "api-middleware"
  ],
  "author": "RockSAMA",
  "license": "MIT",
  "bugs": {
  	"url": "https://github.com/879479119/redux-api-simple-middleware/issues"
  },
  "dependencies": {
    "es6-symbol": "^3.1.0",
    "redux-thunk": "^2.1.0"
  }
}

```

[npm-url]: https://npmjs.org/package/redux-api-simple-middleware
[downloads-image]: http://img.shields.io/npm/dm/redux-api-simple-middleware.svg
[npm-image]: http://img.shields.io/npm/v/redux-api-simple-middleware.svg
[travis-url]: https://travis-ci.org/rocksama/redux-api-simple-middleware
[travis-image]: http://img.shields.io/travis/rocksama/redux-api-simple-middleware.svg
[david-dm-url]:https://david-dm.org/rocksama/redux-api-simple-middleware
[david-dm-image]:https://david-dm.org/rocksama/redux-api-simple-middleware.svg