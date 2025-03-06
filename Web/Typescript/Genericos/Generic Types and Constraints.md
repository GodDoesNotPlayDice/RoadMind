Los tipos genéricos en TypeScript permiten crear componentes que pueden trabajar con una variedad de tipos en lugar de un solo tipo. Esto aumenta la reutilización del código y la flexibilidad.

**Generic Types**: Permiten crear funciones, clases o interfaces que pueden trabajar con múltiples tipos.
    
**Generic Constraints**: Permiten restringir los tipos que se pueden usar con un genérico, asegurando que cumplan con ciertas condiciones.

```ts
function identity<T>(arg: T): T {
    return arg;
}

let output1 = identity<string>("Hola");
let output2 = identity<number>(42);
```

En este ejemplo, `T` es un tipo genérico que puede ser cualquier tipo. La función `identity` puede recibir y devolver cualquier tipo de dato.

## Generic Constraints (Restricciones Genéricas)
A veces, es necesario restringir los tipos que se pueden usar con un genérico. Esto se hace usando **Generic Constraints**.

```ts
interface Lengthwise {
    length: number;
}

function loggingIdentity<T extends Lengthwise>(arg: T): T {
    console.log(arg.length);  // Ahora sabemos que arg tiene una propiedad length
    return arg;
}

loggingIdentity("Hola");  // Funciona porque "Hola" tiene una propiedad length
loggingIdentity([1, 2, 3]);  // Funciona porque los arrays tienen una propiedad length
loggingIdentity(42);  // Error: 42 no tiene una propiedad length
```

En este ejemplo, `T` debe ser un tipo que tenga una propiedad `length`. Esto asegura que solo se puedan pasar tipos que cumplan con esta restricción.

A continuación es [[Decorator]]