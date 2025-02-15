Un **cierre (closure)** es una función que "recuerda" el entorno en el que fue creada, incluso si ese entorno ya no existe. Esto permite que la función acceda a variables de su ámbito exterior incluso después de que ese ámbito haya terminado.

```js
function crearContador() {
    let contador = 0;

    return function() {
        contador++;
        return contador;
    };
}

const incrementar = crearContador();
console.log(incrementar()); // 1
console.log(incrementar()); // 2
```

- La función `crearContador` devuelve una función que "recuerda" la variable `contador`.
- Cada vez que se llama a `incrementar`, se accede y modifica la variable `contador` del ámbito de `crearContador`.


