# Functions

## Definition

There are two ways to define a function, either by assigning it to 

Creating a named function:

```js
function testicle() {
	console.log('poo far');
}

console.log(testicle.name); // testicle
```

if you omit the name, you create an 'anonymous' function. Unless you
immediately invoke it or assign it to a variable you will not be able to refer
to it again.

Assigning to variable:

```js
const testicle = function () {
	console.log('poo far');
}

console.log(testicle.name)// '' (empty string)
```

Assigning to a variable does not give a name to the function. 

```js
const testicle = function () {
	console.log('poo far');
};
```

// TODO fix wording
This means a function can have different name from variable. However, you
cannot call it by it's name. TODO Why can you not call it by its name now?

```js
const testicle = function penis() {
	console.log('poo bar');
};

console.log(testicle.name)// 'penis';

testicle();// 'poo bar'

penis();// ReferenceError
```

The following does work, Though I do not know why you would want to.

```js
function penis() {
	console.log('poo bar');
};

const testicle = penis;

console.log(testicle.name)// 'penis';
testicle();// 'poo bar'
penis();// 'poo bar'
```

(This rest of this section is copied from <http://stackoverflow.com/a/336868>).

The difference is that `functionOne` is defined at run-time, whereas `functionTwo`
is defined at parse-time for a script block. For example:

```js
<script>
  // Error
  functionOne();

  const functionOne = function() {
  };
</script>

<script>
  // No error
  functionTwo();

  function functionTwo() {
  }
</script>
```

This also means you can't conditionally define functions using the second
syntax:

```
<script>
  if (test) {
     // Error or misbehavior
     function functionThree() { doSomething(); }
  }
</script>
```

The above actually defines functionThree irrespective of test's value — unless use strict is in effect, in which case it simply raises an error.

## Parameters & Arguments

First off, a __parameter__ is a variable that is part of a functions signature (function declaration), while
an __argument__ is an actual value passed to a function when calling it (think "actual argument" vs "formal parameter").

In JavaScript, a function does not need to have any parameters defined to allowing passing arguments to it.
All arguments passed to a function are accessible through the special `arguments` array-like variable inside
the function body.

```js
function hasParameters(poo, far, and, succeed) {
	console.log(poo);
	console.log(far);
	console.log(and);
	console.log(succeed);

	console.log(arguments[0]);
	console.log(arguments[1]);
	console.log(arguments[2]);
	console.log(arguments[3]);
}

function lacksParameters() {
	console.log(arguments[0]);
	console.log(arguments[1]);
	console.log(arguments[2]);
	console.log(arguments[3]);
}
```

hasParameters(1, 2, 3);// 1 2 3 undefined 1 2 3 undefined
lacksParameters(1, 2, 3);// 1 2 3 undefined 1 2 3 undefined

## Scopes

JavaScript is lexically scoped, but only function blocks create a new scope
(not if or for blocks for example). (The new `let` and `const` variables are
lexically scoped)

Since functions can be nested inside each other, several degrees of locality
can be created.  Each local scope can see all scopes which contains it.

```js
function() {
	const testicle = 'one ball';

  function() {
    const balls = 'two balls';
    console.log(testicle);
    console.log(balls);
  }
}
console.log(testicle); // ReferenceError
```

## `this`

One of the few tricky things with JavaScript is to understand how `this` is
bound during function calls.

```js
const obj = {
	fnc: function() {
		console.log(this === obj);
		console.log(this === window);
	}
};

const fnc = obj.fnc;

obj.fnc();// true false
fnc();// false true
```

## Function.prototype.bind(thisArg)

+ <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/bind>

Returns a new function which is bound to `thisArg` and has "prefilled"
arguments.  Very similar to LoDash' `_.partial`, except that partial does not
alter the `this` binding.

## Function.prototype.call(thisArg, ...args)

+ <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/call>

Calls a function with `this` bound to `thisArg` and `args` as arguments. Essentially the same as

```js
fnc.call(obj, arg1, arg2);

// is the same as

const boundFnc = fnc.bind(obj);

boundFnc(arg1, arg2);
```

## Function.prototype.apply(thisArg, args)

+ <https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Function/apply>

Similar to `call` but takes an array of arguments, instead of the arguments seperately.

Used to be useful if you had an array of unkown length that you wanted to use
as arguments in a function call.

```js
function org(adverb, verb, noun) {
	console.log(`I'm going to ${adverb} ${verb} your ${noun}`);
}

function ext() {
	// do something
	org.apply(this, arguments);
}
```

With the advent of spread operator we rarely need .apply anymore

```js
function org(adverb, verb, noun) {
	console.log(`I'm going to ${adverb} ${verb} your ${noun}`);
}

function ext(...args) {
  args[2] = 'balls';

	org(...args);
}

ext('gently', 'caress');
```

## Arrow Functions

Arrow functions are a terse way to define anonymous functions. They are identical to 
normal functions in all other ways except one; `this` is inherited from the surrounding
scope and cannot be rebound.

## IIFE (Immediately Invoked Function Express)

IIFEs are functions that are immediately invoked and are mostly used to create
scopes.

```js
(function() {
	const secretTesticle = 'another ball';

	console.log(secretTesticle);
})();
```

Notice the brackets at the end. The following snippet (which does exactly the same
thing) might be a little clearer:

```js
const fnc = function() {
	const secretTesticle = 'another ball';

	console.log(secretTesticle);
}

fnc();
```
