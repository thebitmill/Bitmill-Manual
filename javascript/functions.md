# Functions

## Definition

There are two ways to define a function, either by assigning it to 

Creating a named function:

```
function testicle() {
	console.log('poo far');
}

console.log(testicle.name); // testicle
```

if you omit the name, you create an 'anonymous' function. Unless you
immediately invoke it or assign it to a variable you will not be able to refer
to it again.

Assigning to variable:

```
var testicle = function () {
	console.log('poo far');
}

console.log(testicle.name)// '' (empty string)
```

Assigning to a variable does not give a name to the function. 

```
var testicle = function () {
	console.log('poo far');
};
```

// TODO fix wording
This means a function can have different name from variable. However, you
cannot call it by it's name. TODO Why can you not call it by its name now?

```
var testicle = function penis() {
	console.log('poo bar');
};

console.log(testicle.name)// 'penis';
testicle();// 'poo bar'
penis();// ReferenceError
```

The following does work, Though I do not know why you would want to.

```
function penis() {
	console.log('poo bar');
};

var testicle = penis;

console.log(testicle.name)// 'penis';
testicle();// 'poo bar'
penis();// 'poo bar'
```

(This rest of this section is copied from <http://stackoverflow.com/a/336868>).

The difference is that `functionOne` is defined at run-time, whereas `functionTwo`
is defined at parse-time for a script block. For example:

```
<script>
  // Error
  functionOne();

  var functionOne = function() {
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

## Lexical Scoping

JavaScript is lexically scoped, but only function blocks create a new scope
(not if or for blocks for example).

Since functions can be nested inside each other, several degrees of locality
can be created.  Each local scope can see all scopes which contains it.


```
function() {
	var testicle = 'one ball';
}
console.log(testicle); // ReferenceError
```

```
if(true) {
	var testicle = 'one ball';
}

console.log(testicle); // 'one ball'
```

## IIFE (Immediately Invoked Function Express)

IIFEs are functions that are immediately invoked and are mostly used to create
scopes.

```

(function() {
	var secretTesticle = 'another ball';

	console.log(secretTesticle);
})();
```

Notice the brackets at the end. The following snippet (which does exactly the same
thing) might be a little clearer:

```
var fnc = function() {
	var secretTesticle = 'another ball';

	console.log(secretTesticle);
}

fnc();
```

## Parameters & Arguments

First off, a __parameter__ is a variable that is part of a functions signature (function declaration), while
an __argument__ is an actual value passed to a function when calling it (think "actual argument" vs "formal parameter").

In JavaScript, a function does not need to have any parameters defined to allowing passing arguments to it.
All arguments passed to a function are accessible through the special `arguments` array-like variable inside
the function body.

```
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

hasParameters(1, 2, 3);// 1 2 3 undefined 1 2 3 undefined
lacksParameters(1, 2, 3);// 1 2 3 undefined 1 2 3 undefined

## `this`

```
var obj = {
	fnc: function() {
		console.log(this === obj);
		console.log(this === window);
	}
};

var fnc = obj.fnc;

obj.fnc();// true false
fnc();// false true
```

## Function.prototype.bind

## Function.prototype.call & Function.prototype.apply


```
function org() {
	console.log('testicle');
}

function ext() {
	// do something
	org.apply(this, arguments);
}
```
