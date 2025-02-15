## ¿Qué es un `Set`?
Imagina que tienes una cesta de frutas (un `Set`). En esta cesta, puedes guardar frutas, pero con una regla importante: **no puede haber frutas repetidas**. Es decir, solo puedes tener una manzana y una pera, pero no dos manzanas iguales.

## Caracteristicas de un `Set`
1. **Sin duplicados**: En nuestra cesta de frutas, no puedes tener dos frutas iguales. Si intentas agregar una manzana que ya está en la cesta, no se agregará de nuevo.
2. **Iterable**: Puedes mirar todas las frutas de la cesta una por una.
3. **Métodos útiles**: Puedes agregar frutas, eliminar frutas, verificar si una fruta está en la cesta, y más.

```js
// Crear un Set (nuestra cesta de frutas)
let cesta = new Set();

// Crear algunas frutas
let manzana = { nombre: "Manzana" };
let pera = { nombre: "Pera" };
let otraManzana = { nombre: "Manzana" }; // Otra manzana, pero es un objeto diferente

// Agregar frutas a la cesta
cesta.add(manzana);
cesta.add(pera);
cesta.add(otraManzana); // Se agregará porque es un objeto diferente
cesta.add(manzana); // No se agregará porque ya está en la cesta

// Ver cuántas frutas hay en la cesta
console.log(cesta.size); // 3 (manzana, pera, otraManzana)

// Verificar si una fruta está en la cesta
console.log(cesta.has(manzana)); // true
console.log(cesta.has({ nombre: "Manzana" })); // false (es un objeto diferente)

// Eliminar una fruta de la cesta
cesta.delete(pera);
console.log(cesta.has(pera)); // false

// Iterar sobre las frutas de la cesta
cesta.forEach(fruta => {
  console.log(fruta.nombre);
});
// Salida:
// Manzana
// Manzana (de otraManzana)

// Limpiar la cesta (eliminar todas las frutas)
cesta.clear();
console.log(cesta.size); // 0
```

