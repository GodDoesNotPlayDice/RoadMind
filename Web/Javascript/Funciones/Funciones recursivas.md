
La **recursión** es una técnica en programación donde una función se llama a sí misma para resolver un problema. Es útil para problemas que pueden dividirse en subproblemas más pequeños del mismo tipo.

```js
function factorial(n) {
    if (n === 0 || n === 1) {
        return 1; // Caso base
    } else {
        return n * factorial(n - 1); // Llamada recursiva
    }
}

console.log(factorial(5)); // 120
```

1) La función `factorial` se llama a sí misma con un valor reducido hasta que alcanza el caso base (`n === 0` o `n === 1`).
2) Esto es útil para cálculos como factoriales, Fibonacci, etc.

