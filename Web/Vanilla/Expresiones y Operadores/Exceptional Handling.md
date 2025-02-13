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

## Error Objects
Los objetos de error son utilizados para representar errores que ocurren durante la ejecución del código.

### Tipos de errores incorporados
JavaScript tiene varios tipos de errores incorporados que representan diferentes tipos de excepciones:

- **`Error`**: La clase base para todos los errores.
- **`SyntaxError`**: Se lanza cuando hay un error de sintaxis en el código.
- **`ReferenceError`**: Se lanza cuando se intenta acceder a una variable que no existe.
- **`TypeError`**: Se lanza cuando un valor no es del tipo esperado.
- **`RangeError`**: Se lanza cuando un valor numérico está fuera de su rango permitido.
- **`URIError`**: Se lanza cuando se usan incorrectamente funciones globales de manejo de URI.
- **`EvalError`**: Se lanza cuando ocurre un error en la función `eval()`.


### Crear u lanzar un objeto de error
Puedes crear un objeto de error utilizando el constructor `Error` y luego lanzarlo con `throw`.

```js
try {
    throw new Error("Este es un error personalizado.");
} catch (error) {
    console.error(error.name);    // "Error"
    console.error(error.message); // "Este es un error personalizado."
}
```

### Propiedades de los objetos de error
Los objetos de error tienen varias propiedades útiles:
- **`name`**: El nombre del error (por ejemplo, "Error", "TypeError").
- **`message`**: Un mensaje que describe el error.
- **`stack`**: Una traza de la pila que muestra dónde ocurrió el error (no estándar, pero ampliamente soportado).

```js
try {
    let x = y; // y no está definido, lo que causará un ReferenceError
} catch (error) {
    console.error(error.name);    // "ReferenceError"
    console.error(error.message); // "y is not defined"
    console.error(error.stack);   // Traza de la pila
}
```


### Crea errores personalizados
Puedes crear tus propios tipos de errores extendiendo la clase `Error`.

```js
class MiErrorPersonalizado extends Error {
    constructor(mensaje) {
        super(mensaje);
        this.name = "MiErrorPersonalizado";
    }
}

try {
    throw new MiErrorPersonalizado("Este es un error personalizado.");
} catch (error) {
    console.error(error.name);    // "MiErrorPersonalizado"
    console.error(error.message); // "Este es un error personalizado."
}
```

### Ejemplo completo

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
    console.error("Tipo de error: " + error.name);
    console.error("Traza de la pila: " + error.stack);
} finally {
    console.log("Operación de división finalizada.");
}
```

