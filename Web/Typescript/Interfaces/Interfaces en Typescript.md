En TypeScript, tanto `type` como `interface` se utilizan para definir la forma de los objetos, pero tienen unas diferencias.

**Interfaces**: Son más adecuadas para definir la forma de un objeto y pueden ser extendidas o implementadas por clases

```ts
interface Person {
  name: string;
  age: number;
}
```

**Types**: Son más flexibles y pueden definir no solo la forma de un objeto, sino también uniones, intersecciones, y otros tipos complejos.

```ts
type Person = {
  name: string;
  age: number;
};
```

## Extending Interfaces
Las interfaces pueden extenderse para crear nuevas interfaces que incluyan las propiedades de las interfaces originales.

```ts
interface Person {
  name: string;
  age: number;
}

interface Employee extends Person {
  employeeId: number;
}
```

## Interface Declaration
La declaración de una interface es sencilla. Simplemente defines las propiedades y sus tipos.

```ts
interface User {
  id: number;
  username: string;
  email: string;
}
```

## Hybrid Types
TypeScript permite crear tipos híbridos que pueden actuar como funciones y objetos al mismo tiempo.

```ts
// Definimos una interfaz híbrida
interface Counter {
    // La interfaz puede ser invocada como una función
    (start: number): string;
    
    // También tiene una propiedad
    interval: number;
    
    // Y un método
    reset(): void;
}

// Implementamos la función que cumple con la interfaz híbrida
function createCounter(): Counter {
    // Definimos la función que actúa como contador
    let counter = function (start: number) {
        console.log(`Counter started at ${start}`);
    } as Counter;

    // Añadimos la propiedad 'interval'
    counter.interval = 5;

    // Añadimos el método 'reset'
    counter.reset = function () {
        console.log("Counter has been reset");
    };

    return counter;
}

// Usamos la función híbrida
let myCounter = createCounter();

// Invocamos la función
myCounter(10); // Output: Counter started at 10

// Accedemos a la propiedad
console.log(myCounter.interval); // Output: 5

// Llamamos al método
myCounter.reset(); // Output: Counter has been reset
```

- **Interfaz Híbrida**: La interfaz `Counter` define que el objeto puede ser invocado como una función que toma un número y devuelve un string. También tiene una propiedad `interval` y un método `reset`.
    
- **Implementación**: La función `createCounter` crea un objeto que cumple con la interfaz `Counter`. Este objeto puede ser invocado como una función y también tiene propiedades y métodos adicionales.
    
- **Uso**: Creamos una instancia de `Counter` usando `createCounter`. Luego, podemos invocar la función, acceder a la propiedad `interval`, y llamar al método `reset`.