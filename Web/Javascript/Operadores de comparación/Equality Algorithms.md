Un **algoritmo de comparación** es un conjunto de reglas o pasos que define **cómo se comparan dos valores** en un lenguaje de programación.

Tenemos 
- `isLooselyEqual`
- `isStrictlyEqual`
- `SameValueZero`
- `SameValue`

## isLooselyEqual
Este algoritmo es el que se usa cuando comparas con `==`. Realiza una comparación **débil**, es decir, intenta convertir los valores a un tipo común antes de compararlos.

Hace exactamente lo mismo que `==`

```js
console.log(5 == "5"); // true
```

## isStrictlyEqual
Este algoritmo es el que se usa cuando comparas con `===`. Realiza una comparación **estricta**, es decir, compara tanto el valor como el tipo de dato sin hacer conversiones.

Hace exactamente lo mismo que `===`

```js
console.log(5 === "5"); // false
```

## SameValueZero
Este algoritmo es similar a `IsStrictlyEqual`, pero trata `NaN` como igual a `NaN` y no distingue entre `-0` y `0`. Es el que se usa en estructuras como `Set` y `Map`.

```js
let set = new Set();
set.add(NaN);
console.log(set.has(NaN)); // true
```

¿Qué es lo que hace `SameValueZero`?
1) Compara valores y tipos estrictamente.
2) Considera `NaN` como igual a `NaN`
3) No distingue entre `-0` y `0`

## SameValue
**Igualdad estricta con tratamiento especial para `NaN` y `-0`**

Este algoritmo es el que se usa en `Object.is`. Compara y valores y tipos estrictamente, pero distingue entre `-0` y `0`, y trata `NaN` como igual a `NaN`.

```js
console.log(Object.is(NaN, NaN)); // true
console.log(Object.is(-0, 0));   // false
```
