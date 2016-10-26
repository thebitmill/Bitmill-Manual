# Prototype

One of the few ways you can truly fail in JavaScript programming, is trying to
think in the same ways that you do with normal Object Oriented Programming.
This is so important, it gets its own, short, section. Make sure you read and
fully understand the entire 2 Pillars section

Many people call JavaScript implementation Prototypal Inheritance, but this is
also not entirely correct. The word inheritance in itself is misleading in this
context. Instead of behaviour inheritance, one should look at is as behaviour
delegation.

Instead of each subclass inheriting their own version of a method, methods
are simply searched for up the prototype chain.

## Normal Inheritance is Overrated

+ <http://lionelbarrow.com/2016/03/19/inheritance-is-terrible/>
+ <https://github.com/raganwald-deprecated/homoiconic/blob/master/2010/12/oop.md#readme>

## Inheritance / Prototypal Delegation in JavaScript

1. [JS Objects, Part 1: Inherited a Mess](https://davidwalsh.name/javascript-objects)
2. [JS Objects, Part 2: Distractions](https://davidwalsh.name/javascript-objects-distractions)
3. [JS Objects, Part 3: De"construct"ion](https://davidwalsh.name/javascript-objects-deconstruction)
