# ES6 Modules

In the [next version of JavaScript (ES6)](ES6), modules are added in and are inspired by popular JavaScript module loaders (AMD, CommonJS). Here is what they look like:

```js
// app.js
// exporting a function
export function Hello(name) {
  return 'Hello ' + name;
}

// exporting variables
export let key = '3840';
export let obj = {
  foo: 1,
  bar: 2
};
```

What this looks like in ES5:

```js
// exporting a function
exports.Hello = function(name) {
  return "Hello " + name;
};

// exporting variables
var key = exports.key = "3840";
var obj = exports.obj = {
  foo: 1,
  bar: 2
};
```

Importing them is similiar to python with the import from syntax. In ES5, you would use `require`.

```js
import Hello from 'app'
```

You can also use `default` which is similiar to `module.exports` in ES5.

```js
// hero.js
export default class Hero {
  constructor(name) {
    this.name = name;
  }

  say() {
    console.log('Hello ' + name);
  }
}
```

[ES6]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/New_in_JavaScript/ECMAScript_6_support_in_Mozilla
