
## Top Types
Los **top types** son tipos que pueden representar cualquier valor. En TypeScript, los principales top types son `unknown` y `any`.

### Unknown
Este tipo es una alternativa más segura a `any`. Una variable de tipo `unknown` puede contener cualquier valor, pero no puedes realizar operaciones con ella sin primero asegurarte de su tipo. Esto ayuda a prevenir errores en tiempo de ejecución.

```ts
let value: unknown;

value = "Hello World"; // OK
value = 42; // OK
value = true; // OK

if (typeof value === "string") {
    console.log(value.toUpperCase()); // Ahora TypeScript sabe que es un string
}
```
### Any
Este tipo es el más flexible y permite que una variable contenga cualquier valor y que se realicen operaciones sin restricciones. Sin embargo, su uso puede llevar a la pérdida de las ventajas de TypeScript, como la detección de errores en tiempo de compilación.

```ts
let value: any;

value = "Hello World"; // OK
value = 42; // OK
value = true; // OK

console.log(value.toUpperCase()); // No hay error en tiempo de compilación, pero puede fallar en tiempo de ejecución
```

## Bottom Types
Los **bottom types** son tipos que no pueden contener ningún valor. En TypeScript, el principal bottom type es `never`.

### Never
Este tipo representa valores que nunca ocurren. Se utiliza comúnmente para funciones que nunca retornan (por ejemplo, lanzan una excepción o entran en un bucle infinito) o para indicar situaciones imposibles.

```ts
 function error(message: string): never {
    throw new Error(message);
}

function infiniteLoop(): never {
    while (true) {}
}

function fail(): never {
    return error("Something failed");
}
```

