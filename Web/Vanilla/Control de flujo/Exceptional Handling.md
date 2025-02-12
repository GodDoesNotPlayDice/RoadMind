El manejo de excepciones es una técnica que te permite manejar errores o situaciones inesperadas en tu código sin que el programa se detenga abruptamente.

Los bloques `try`, `catch`, `finally` y la declaración `throw`.

- **`try`**: Bloque de código que podría generar una excepción.
- **`catch`**: Bloque que maneja la excepción si ocurre.
- **`finally`**: Bloque que siempre se ejecuta, independientemente de si hubo una excepción o no.
- **`throw`**: Lanza una excepción personalizada.

## Bloques

Ejemplo del uso completo.
```js
function dividir(a, b) {
    if (b === 0) {
        throw new Error("División por cero no permitida.");
    }
    return a / b;
}

try {
    let resultado = dividir(10, 0);
    console.log("El resultado es: " + resultado);
} catch (error) {
    console.error("Error: " + error.message);
} finally {
    console.log("Operación de división finalizada.");
}
```

### try...catch
El bloque `try` contiene el código que podría generar una excepción. Si ocurre un error, el control se pasa al bloque `catch`, donde puedes manejar la excepción.

```js
try {
    // Código que podría generar una excepción
    let resultado = 10 / 0;
    if (resultado === Infinity) {
        throw new Error("División por cero no permitida.");
    }
    console.log("El resultado es: " + resultado);
} catch (error) {
    // Manejo de la excepción
    console.error("Ocurrió un error: " + error.message);
}
```

### finally
El bloque `finally` se ejecuta siempre, independientemente de si se lanzó una excepción o no. Es útil para liberar recursos o realizar limpieza.

```js
try {
    console.log("Intentando ejecutar el código.");
    throw new Error("Este es un error simulado.");
} catch (error) {
    console.error("Error capturado: " + error.message);
} finally {
    console.log("Este bloque siempre se ejecuta.");
}
```


### throw
La declaración `throw` te permite lanzar una excepción personalizada. Puedes lanzar cualquier tipo de dato, pero es común usar objetos `Error`.

```js
function verificarEdad(edad) {
    if (edad < 18) {
        throw new Error("Debes ser mayor de edad.");
    }
    console.log("Acceso permitido.");
}

try {
    verificarEdad(15);
} catch (error) {
    console.error(error.message); // "Debes ser mayor de edad."
}
```

