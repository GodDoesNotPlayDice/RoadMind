En JavaScript es una funcionalidad que te permite escribir código de manera más segura y con menos probabilidades de cometer errores. Cuando activas el modo estricto, el intérprete de JavaScript aplica un conjunto más estricto de reglas al analizar y ejecutar tu código.

Para activar el modo estricto, simplemente añade la siguiente línea al principio de tu script o función:

```js
"use strict";
```

**Ejemplo**:
```js
"use strict";

// Tu código aquí
x = 10; // Esto lanzará un error porque 'x' no está declarado
console.log(x);
```

```js
function miFuncion() {
    "use strict";

    // Tu código aquí
    y = 20; // Esto lanzará un error porque 'y' no está declarado
    console.log(y);
}

miFuncion();
```  

## Cambios que este introduce

**Variables no declaradas**: En modo estricto, asignar un valor a una variable no declarada lanzará un error.

```js
"use strict";
x = 10; // ReferenceError: x is not defined
```

**Eliminación de `with`**: El uso de la declaración `with` no está permitido en modo estricto.

```js
"use strict";
with (Math) { x = cos(2) }; // SyntaxError: Strict mode code may not include a with statement
```

**Parámetros duplicados**: No se permiten parámetros duplicados en la definición de funciones.

```js
"use strict";
function suma(a, a, c) { // SyntaxError: Duplicate parameter name not allowed in this context
    return a + a + c;
}
```

**Propiedades de solo lectura**: Intentar asignar un valor a una propiedad de solo lectura lanzará un error.

```js
"use strict";
var obj = {};
Object.defineProperty(obj, "x", { value: 42, writable: false });
obj.x = 9; // TypeError: Cannot assign to read only property 'x' of object '#<Object>'
```

**Eliminación de `arguments.callee`**: No se puede acceder a `arguments.callee` en modo estricto.

```js
"use strict";
function factorial(n) {
    if (n <= 1) return 1;
    return n * arguments.callee(n - 1); // TypeError: 'caller', 'callee', and 'arguments' properties may not be accessed on strict mode functions or the arguments objects for calls to them
}
```

`callee` es una propiedad del objeto `arguments` en JavaScript que hace referencia a la función que se está ejecutando actualmente. Es útil en contextos donde necesitas referirte a la función desde dentro de sí misma, como en funciones recursivas.

Sin embargo, el uso de `arguments.callee` está desaconsejado en el modo estricto (`"use strict"`) y en versiones modernas de JavaScript debido a problemas de rendimiento y mantenimiento del código.

### Problemas con Callee
1. **Rendimiento**: El uso de `arguments.callee` puede ser menos eficiente porque impide algunas optimizaciones que el motor de JavaScript podría realizar.
2. **Mantenimiento**: Hace que el código sea más difícil de entender y mantener, ya que la referencia a la función no es explícita.
3. **Modo estricto**: En el modo estricto, `arguments.callee` no está permitido y lanzará un error.

#### Alternativa moderna
En lugar de usar `arguments.callee`, puedes simplemente nombrar la función y usar ese nombre para la recursión:

```js
function factorial(n) {
    if (n <= 1) return 1;
    return n * factorial(n - 1); // Llamada recursiva usando el nombre de la función
}

console.log(factorial(5)); // 120
```

