`this` en JavaScript es un concepto fundamental que puede resultar un poco confuso al principio, pero es muy poderoso una vez que lo entiendes.

`this` se refiere al contexto en el que se ejecuta una función, y su valor puede cambiar dependiendo de cómo y dónde se utilice.

## En un método de objeto
Cuando `this` se usa dentro de un método de un objeto, se refiere al objeto que contiene el método.

```js
const coche = {
  marca: "Toyota",
  arrancar: function() {
    console.log("El coche " + this.marca + " está arrancando.");
  }
};

coche.arrancar(); // Output: El coche Toyota está arrancando.
```

En este caso, `this` se refiere al objeto `coche`.

## En una función  regular
En una función regular (no arrow function), `this` se refiere al objeto global (`window` en el navegador, `global` en Node.js) si la función no está en modo estricto. En modo estricto (`strict mode`), `this` será `undefined`.

```js
function mostrarThis() {
  console.log(this);
}

mostrarThis(); // En el navegador, esto imprimirá el objeto `window`

"use strict";
function mostrarThisStricto() {
  console.log(this);
}

mostrarThisStricto(); // Output: undefined
```

## En una arrow function
Las arrow functions no tienen su propio `this`. En su lugar, `this` se refiere al contexto en el que la arrow function fue definida (lexical scope). [[Funciones]]

```js
const objeto = {
  valor: 42,
  metodo: function() {
    const arrowFunc = () => {
      console.log(this.valor);
    };
    arrowFunc();
  }
};

objeto.metodo(); // Output: 42
```

Aquí, `this` dentro de la arrow function se refiere al `this` del método `metodo`, que es el objeto `objeto`.

## En un evento
Cuando `this` se usa en un manejador de eventos, se refiere al elemento que recibió el evento.

```js
document.querySelector("button").addEventListener("click", function() {
  console.log(this); // `this` se refiere al botón que fue clickeado
});
```


## En el contexto global
Fuera de cualquier función o método, `this` se refiere al objeto global (`window` en el navegador, `global` en Node.js).

```js
console.log(this); // En el navegador, esto imprimirá el objeto `window`
```

## Function Borrowing

### Que es?
Es una técnica que permite "tomar prestado" un método de un objeto y usarlo en otro objeto. Esto es útil para reutilizar código y evitar la duplicación de métodos.

**Function Borrowing** (préstamo de funciones) en JavaScript permite utilizar métodos de un objeto en otro objeto sin necesidad de duplicar el código. Esto se logra utilizando los métodos `.call()`, `.apply()` o `.bind()`, que permiten establecer explícitamente el valor de `this` en una función.

### ¿Como funciona?
1. **`.call()`**: Llama a una función con un valor específico para `this` y argumentos individuales.
2. **`.apply()`**: Similar a `.call()`, pero los argumentos se pasan como un array.
3. **`.bind()`**: Crea una nueva función con `this` fijado a un valor específico, pero no la ejecuta inmediatamente..

```js
const persona1 = {
  nombre: "Ana",
  saludar: function() {
    console.log("Hola, mi nombre es " + this.nombre);
  }
};

const persona2 = {
  nombre: "Carlos"
};

// Usando .call() para "prestar" el método saludar a persona2
persona1.saludar.call(persona2); // Output: Hola, mi nombre es Carlos

// Usando .apply() para hacer lo mismo
persona1.saludar.apply(persona2); // Output: Hola, mi nombre es Carlos

// Usando .bind() para crear una nueva función con `this` fijado a persona2
const saludarCarlos = persona1.saludar.bind(persona2);
saludarCarlos(); // Output: Hola, mi nombre es Carlos
```

### ¿Cuándo usar Function Borrowing?
- Cuando quieres reutilizar un método en varios objetos sin duplicar código.
- Cuando necesitas que un método funcione en un contexto diferente al original.
### Diferencia entre `.call()`, `.apply()` y `.bind()`
| Método     | Descripción                                                                                        |
| ---------- | -------------------------------------------------------------------------------------------------- |
| `.call()`  | Llama a la función con un valor específico para `this` y argumentos individuales.                  |
| `.apply()` | Similar a `.call()`, pero los argumentos se pasan como un array.                                   |
| `.bind()`  | Crea una nueva función con `this` fijado a un valor específico, pero no la ejecuta inmediatamente. |

### Ejemplo practico
Imagina que tienes un método para calcular el área de un rectángulo en un objeto, y quieres usarlo en otro objeto que representa un cuadrado:

```js
 const rectangulo = {
  ancho: 10,
  alto: 5,
  area: function() {
    return this.ancho * this.alto;
  }
};

const cuadrado = {
  ancho: 7,
  alto: 7
};

// Usando .call() para calcular el área del cuadrado
const areaCuadrado = rectangulo.area.call(cuadrado);
console.log(areaCuadrado); // Output: 49
```

