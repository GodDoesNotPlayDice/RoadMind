las funciones son bloques de código que realizan una tarea específica y pueden ser reutilizados en diferentes partes de un programa.

## Función tradicional y flecha
Las funciones pueden recibir parámetros (**entradas**) y devolver un valor (**salida**).

Una forma tradicional de definir una `función`, y mas antigua, la diferencia de esta es que puedes usar la palabra `this` dentro de ella como si de una clase se tratase.

`return`: hace que una función devuelva un valor.

Los parámetros pueden definirse como **obligatorios o opcionales** si se le asigna un valor en su declaración ej. `apellido = ""` 

[[Tipos de funciones]]

## Rest
 Ademas existe los parámetros **rest** los cuales su función es aceptar indefinido números de argumentos así como un array.
 
```js
function sumar(...numeros) {
    return numeros.reduce((total, num) => total + num, 0);
}

console.log(sumar(1, 2, 3, 4)); // Output: 10
```


**Tradicional**
 ```js
function saludar(nombre, apellido = "") {
    return "Hola, " + nombre + " " + apellido;
}

console.log(saludar("Juan")); // Output: Hola, Juan
```

**Moderna (arrow function)** 
No se puede usar `this` para crear un objeto.

```js
const saludar = (nombre) => {
    return "Hola, " + nombre;
};

console.log(saludar("Carlos")); // Output: Hola, Carlos
```


## IIFEs
Es expresión de la función invocada inmediatamente es una función que se ejecuta inmediatamente después de la creación.

```js
(() => {
    
    const x = 1;
    const y = 9;

    console.log(`Hello, The Answer is ${x+y}`);

})();
```


## Arguments object
**Es preferible usar rest hoy en día*

El objeto `arguments` es una característica de las funciones en JavaScript que te permite acceder a todos los argumentos pasados a la función, incluso si no están definidos en la lista de parámetros de la función.


```js
function muestraArgumentos() {
    for (let i = 0; i < arguments.length; i++) {
        console.log(`Argumento ${i}: ${arguments[i]}`);
    }
}

muestraArgumentos(1, 2, 3, "Hola");
```

En este ejemplo, la función `muestraArgumentos` no tiene parámetros definidos, pero puedes pasarle cualquier número de argumentos. Dentro de la función, `arguments` es un objeto similar a un array que contiene todos los argumentos pasados. El bucle `for` recorre `arguments` y muestra cada argumento en la consola.

Es importante notar que `arguments` no es un array real, sino un objeto similar a un array. Esto significa que no tiene métodos de array como `forEach` o `map`. Sin embargo, puedes convertirlo en un array si lo necesitas:

```js
function muestraArgumentos() {
    const argsArray = Array.from(arguments);
    argsArray.forEach((arg, index) => {
        console.log(`Argumento ${index}: ${arg}`);
    });
}

muestraArgumentos(1, 2, 3, "Hola");
```

En este segundo ejemplo, `Array.from(arguments)` convierte el objeto `arguments` en un array real, lo que te permite usar métodos de array como `forEach`.


## Functions Scope
El **scope** se refiere al contexto en el que una variable o función puede ser accedida o utilizada. En JavaScript, hay varios tipos de alcance:

### Global Scope (Ámbito global)
Las variables o funciones declaradas en el ámbito global están disponibles en todo el código.

Mala practica usar `var`

```js
var globalVar = "Soy global";

function muestraGlobal() {
    console.log(globalVar); // Acceso a la variable global
}

muestraGlobal(); // Output: "Soy global"
```

### Module Scope (Ámbito de Modulo)
En módulos de JavaScript (archivos con `import`/`export`), las variables declaradas en el ámbito del módulo no son globales, sino que están limitadas al módulo.

```js
// module.js
let moduleVar = "Soy del módulo";
export { moduleVar };
```

### Function Scope (Ámbito de función)
Las variables declaradas dentro de una función solo son accesibles dentro de esa función.

```js
function muestraLocal() {
    let localVar = "Soy local";
    console.log(localVar); // Acceso dentro de la función
}

muestraLocal(); // Output: "Soy local"
console.log(localVar); // Error: localVar no está definida
```

### Block Scope (Ámbito de bloque)
Las variables declaradas con `let` o `const` dentro de un bloque (`{}`) solo son accesibles dentro de ese bloque.

```js
if (true) {
    let blockVar = "Soy de bloque";
    console.log(blockVar); // Acceso dentro del bloque
}

console.log(blockVar); // Error: blockVar no está definida
```


## Function Stack (Pila de llamadas)
La **pila de llamadas** es un mecanismo que JavaScript utiliza para rastrear las funciones que se están ejecutando. Cuando una función llama a otra, esta se agrega a la pila. Cuando la función termina, se elimina de la pila.

```js
function primera() {
    console.log("Primera función");
    segunda();
}

function segunda() {
    console.log("Segunda función");
    tercera();
}

function tercera() {
    console.log("Tercera función");
}

primera();
```

1. Cuando se llama a `primera()`, esta se agrega a la pila.
2. Dentro de `primera()`, se llama a `segunda()`, que se agrega a la pila.
3. Dentro de `segunda()`, se llama a `tercera()`, que se agrega a la pila.
4. Cuando `tercera()` termina, se elimina de la pila.
5. Luego, `segunda()` termina y se elimina de la pila.
6. Finalmente, `primera()` termina y se elimina de la pila.

## Built-in functions
En JavaScript, un **método** es una función que está asociada a un objeto. Los métodos son acciones que los objetos pueden realizar. Para diferenciar entre propiedades y métodos:

**Propiedad**: Es un valor asociado a un objeto (por ejemplo, `objeto.propiedad`).
**Método**: Es una función asociada a un objeto (por ejemplo, `objeto.metodo()`).

### Objetos incorporados (Built in)

Ejemplos de **built in**

#### Objeto `string`:
Métodos para manipular cadenas de texto

```js
let mensaje = "Hola Mundo";
console.log(mensaje.toUpperCase()); // "HOLA MUNDO"
console.log(mensaje.indexOf("Mundo")); // 5
```

#### Objeto `Array`: 
Métodos para manipular arrays.

```js
let numeros = [1, 2, 3, 4];
numeros.push(5); // Añade un elemento al final
console.log(numeros); // [1, 2, 3, 4, 5]
console.log(numeros.join(", ")); // "1, 2, 3, 4, 5"
```


#### Objeto `Math`:
Métodos para operaciones matemáticas.

```js
console.log(Math.sqrt(16)); // 4
console.log(Math.random()); // Número aleatorio entre 0 y 1
```


#### Objeto `Date`:
Métodos para trabajar con fechas y horas.

```js
let fecha = new Date();
console.log(fecha.getFullYear()); // Año actual
console.log(fecha.getMonth()); // Mes actual (0-11)
```

### Custom Built
También puedes agregar métodos a tus propios objetos:

```js
let coche = {
    marca: "Toyota",
    modelo: "Corolla",
    arrancar: function() {
        console.log("El coche está arrancando...");
    }
};

coche.arrancar(); // "El coche está arrancando..."
```

