## Arrays
Un **Array** en JavaScript es una lista ordenada de valores que pueden ser de cualquier tipo, incluyendo números, strings, objetos, e incluso otros arrays. Los arrays son dinámicos, lo que significa que pueden crecer o reducirse en tamaño según sea necesario. Puedes acceder a los elementos de un array utilizando su índice numérico, que comienza desde 0.

```js
let frutas = ["Manzana", "Banana", "Cereza"];
console.log(frutas[0]); // Salida: "Manzana"
```

## Typed Arrays
Los **Typed Arrays** son una característica más reciente de JavaScript que proporciona una forma de manejar datos binarios en un buffer. A diferencia de los arrays regulares, los Typed Arrays están diseñados para trabajar con datos binarios de manera eficiente, lo que es útil en aplicaciones como el procesamiento de gráficos, manipulación de archivos binarios, y comunicación con APIs de bajo nivel.

Los Typed Arrays no son arrays en el sentido tradicional, sino que son vistas sobre un **ArrayBuffer**, que es un objeto que representa un bloque de memoria binaria. Los Typed Arrays permiten leer y escribir datos en este buffer de manera estructurada, con tipos de datos específicos como `Int8`, `Uint32`, `Float64`, etc.

```js
let buffer = new ArrayBuffer(16); // Crea un buffer de 16 bytes
let int32View = new Int32Array(buffer); // Crea una vista de 32 bits (4 bytes por elemento)

int32View[0] = 42;
console.log(int32View[0]); // Salida: 42
```

