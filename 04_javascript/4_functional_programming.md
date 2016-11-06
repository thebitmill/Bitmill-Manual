# Functional Programming

1. [The Two Pillars of JavaScript, Part 2 (Functional Programming): How To Stop Micromanaging Everything](https://medium.com/javascript-scene/the-two-pillars-of-javascript-pt-2-functional-programming-a63aa53a41a4#.268j39loi)
2. [Wikipedia: Functional Programming](https://en.wikipedia.org/wiki/Functional_programming)

## Map, Reduce & Filter

These 3 functions are very important in a functional programmers arsenal. They
have long been available through libraries like Lodash, but are now commonly
available on the `Array.prototype`.

+ <http://cryto.net/~joepie91/blog/2015/05/04/functional-programming-in-javascript-map-filter-reduce/>

Be sure to check out the full list of Array.prototype methods (can be found at
[MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array)),
and also all collection and array methods in the [LoDash documentation](https://lodash.com/docs).

### Filter

Easiest to grasp. Simply returns an new Array without any values that do not pass
the predicate.

### Map

Essentially maps one value to another.

Can be used to some cool stuff sith `String.protoype.split` and
`String.prototype.join`, eg `str.sprit(',').map(func).join()`.

TODO Example of above

### Reduce

Often used to reduce several values into one out, but can also be used to
construct new arrays or objects.

A good example of a "constructing" reduce is replacing
a `arr.filter().map()` chain. Instead of having to iterate
over and create two new arrays, we could simply

```js
arr = arr.reduce(function(seed, value) {
	if(test(value)) {
		seed.push(manipulat(value);
	}

	return seed;
}, []);
```

### Try To Avoid Loop

`.forEach` loop is simple to replace with a for loop. Even `_.forEach` on
objects is now easily implemented with for-of loops, but these loops should
generally be avoided. Methods using callbacks to iterate should be preferred
because:

1. More modular code, you can reuse a previous function
2. Can handle asyncronous data. Ie data generated from events or streams.

The only reason to use good old `for` loops these are for performance.

## Books

- O'Reilly, Functional JavaScript: Introducing Functional Programming With
  Underscore.js (2013)
