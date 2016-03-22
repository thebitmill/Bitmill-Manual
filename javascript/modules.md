# Modules

JavaScript was never really constructed with modularity in mind. Everything is
global solves every problem. That was the philosophy. CommonJS puts an end to
this. Node is completely built around CommonJS modules, and you basically have
to write CommonJS modules for your JavaScript to work with Node.

## RequireJS

Poo. Real asyncronous poo. Generally hated by every that has tried it at TCB.
Try Browserify instead. If you need Lazy Loading, find a good CommonJS, async
loader. ES6 loader is coming soon as well.

# Modules CommonJS & NPM moduler

## CommonJS

JavaScript is in its purest form very unmodular. In a static html page with a
script tag loading an external file or inserting inline code, all variables
defined will be placed in the global scope. Any code loaded or inserted
afterwards will have full access to all previously defined variables. Good code
ethics advocates not polluting the global scope, and in pure JavaScript this is
easily avoided buying using closures and immediately-invoked function
expressions (IIFE's).

However, further structure is obviously desired. CommonJS attempts to solve
much of the this structuring by defining a module format. It is important to
note that CommonJS is not native JavaScript and only works in specific
environments (eg. Node.js & Browserify). With CommonJS, essentially a single
file can and does constitute an entire module. All variables defined in this
file are contained in a scope only available in that file; only properties
attached to the module.exports object will be returned from that file/module.
(In practice, when one refers to CommonJS modules, usually one is not referring
to single files; but rather modules made of several "modulirized" files)


```js
// file: module.js
var private = 'sum intriguing secretz.';
var public = 'don care ifz u readz thiz.';

var whistleBlower = function(){
  return private;
};

module.exports = {
  public: public,
  whistleBlower: whistleBlower
};
```

To require the above file (module.js) from the same folder as the current file:

```js
// file: app.js
var module = require('./module.js');
```

console.log(module.public);//'don care ifz u readz thiz.'
console.log(module.private);//undefined
console.log(module.whistleBlower());//'sum intriguing secretz.'
```

### module.exports vs exports

Many people are confused by the difference between module.exports and exports in CommonJS modules. It is, however, quite elementary. When a module is initiated, an express variables containing a simple reference to module.exports object is created. Essentially, as if the following line had been executed:

```js
var exports = module.exports;
```

This is simply done as a convenience to the module developer, only
module.exports actually gets exported. This means, assigning properties to
module.exports or exports does exactly the same thing. Ie., the following are
identical:

```js
module.exports.prop = 'value';
exports.prop = 'value';
```

However, if you reassign the exports variable, the reference is lost. This
means the following will not work because exports no longer points to the same
object as module.exports.

```js
exports = {};
exports.prop = 'value';
```

Now, whatever (if anything) was assigned to module.exports prior to those
statements would get returned.

## ES6 Modules

Not yet available in any environment (include Node v0.5.X).
