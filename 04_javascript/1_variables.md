# Variables

## Hoisting

```
console.log(poo);// undefined

var poo = 'far';

console.log(poo);// 'far'
```

```
console.log(poo);// undefined
console.log(far);// ReferenceError

var poo = 'far';
```

## Scopes

### Block vs Function Scope

`var` is function scoped, `let` and `const` are block scoped.

### Temporal Dead Zone

<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/let#Temporal_dead_zone_and_errors_with_let>
