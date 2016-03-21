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
