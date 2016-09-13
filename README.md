# redux-api-simple-middleware
[![NPM version][npm-image]][npm-url] [![Downloads][downloads-image]][npm-url] [![Build Status][travis-image]][travis-url]
---
A simple and useful solution to control the network activities of your Redux app;

It is based on Redux,so I didn't write that in `package.json`

## Simple use with this middleware

+ There is a good example built with react native and redux, [bilibili-react-native](https://github.com/879479119/Bilibili-React-Native),it's in the recommendPage.js

+ run `npm install redux-api-simple-middleware --save` in your project first

+ import it in your `configStore.js` file(the file that you create a store and add other middleware) with:
`import apiMiddleware from 'redux-api-simple-middleware'`,then append the middleware to the `applyMiddleware` function like:

```
export default function configureStore(initialState) {
  return createStore(
    rootReducer,
    initialState,
    compose(
      applyMiddleware(
        thunkMiddleware,
        apiMiddleware
      )
    )
  )
}
```

+ after you have configured the store,you may add the `SimpleAPIReducer` to your rootReducer like:

```
import {combineReducers} from 'redux'
import {SimpleAPIReducer} from 'redux-api-simple-middleware'

...

const rootReducer = combineReducers ({
  //maybe some other reducers
  SimpleAPIReducer,
})

export default rootReducer
```

+ if you got all the above steps done,congrantulations,you can start to use it in your project

+ here is a example(I assume that you can work with Redux easily ^_^):

```
import {fetchBackSymbol} from 'redux-api-simple-middleware'

const log = fetchBackSymbol('http://app.bilibili.com/x/banner?plat=4')
 //you have to keep the returned value,it's a unique object that can help you get the relevent response

...

//where you need to render with the fetchState,you can find a state named 'SMAfetchState'

const {SAMfetchState, symbol, data} = this.props

if(SAMfetchState == 1){
  return 
}else if(SAMfetchState == 2){
  if(symbol == log){
    renderData = Object.assign({}, data)
  }
  return renderData
}

...
//I dont want to make it more difficult,but in fact,you must add the states in the page(Redux)

const mapStateToProps = (state) => ({
  SAMfetchState:state.SimpleAPIReducer.SAMfetchState,
  data:state.SimpleAPIReducer.data,
  symbol:state.SimpleAPIReducer.symbol
})

export default connect(mapStateToProps, {
  fetchBackSymbol
})(YOUR_COMPONENT_NAME)
```

+ here goes the package.json

```

{
  "name": "redux-api-simple-middleware",
  "version": "1.0.1",
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