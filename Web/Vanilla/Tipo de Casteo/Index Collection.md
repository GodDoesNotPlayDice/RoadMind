Las colecciones indexadas son colecciones que tienen índices numéricos, es decir, las colecciones de datos ordenadas por un valor de índice. En JavaScript, una matriz es una colección indexada. Una matriz es un conjunto ordenado de valores que tiene un índice numérico.

## Arrays
Imagina un **array** como una caja de frutas donde cada posición está numerada (empezando desde `0`):

```js
// Un array con peras y manzanas (índices 0, 1, 2)
const frutas = ["pera", "manzana", "pera"];
```

#### Características
- **Índices numéricos**: Accedes a los elementos por su posición.
- **Flexible**: Puedes mezclar tipos de datos (frutas, números, etc.).
- **Dinámico**: Puedes agregar o quitar elementos cuando quieras.

**Ejemplo**

```js
// Acceder al elemento en el índice 1
console.log(frutas[1]); // "manzana"

// Agregar una fruta al final
frutas.push("manzana");
console.log(frutas); // ["pera", "manzana", "pera", "manzana"]

// Eliminar la última fruta
frutas.pop();
console.log(frutas); // ["pera", "manzana", "pera"]
```

## Typed Arrays
Son como **cajas especializadas** para un solo tipo de dato (ej: números).  
Imagina que tienes una caja solo para manzanas 🍎 (no puedes meter peras aquí):

```js
// Crear un Typed Array para números (ej: 8 bytes)
const numeros = new Uint8Array([10, 20, 30]);
```

### Características
- **Tipos fijos**: Solo almacenan un tipo de dato (números enteros, flotantes, etc.).
- **Eficiencia**: Son más rápidos y consumen menos memoria que los arrays normales.@
- **Tamaño fijo**: No puedes agregar/eliminar elementos después de crearlos.

| **Característica** | **Array** (🍐🍎)        | **Typed Array** (Solo 🍎)       |
| ------------------ | ----------------------- | ------------------------------- |
| Tipos de datos     | Cualquiera              | Solo un tipo (ej: números)      |
| Tamaño             | Dinámico (puede crecer) | Fijo (definido al crear)        |
| Rendimiento        | Menos eficiente         | Muy eficiente                   |
| Uso común          | Listas generales        | Datos binarios, imágenes, audio |

## ¿Cuando usar cada uno?

**Array**: Si necesitas una lista flexible con distintos tipos de datos (como mezclar peras y manzanas)

**Typed Array**: Si trabajas con datos numéricos pesados (como procesamiento de imagenes, audio, etc)

```js
// Array de frutas
const frutas = ["pera", "manzana"];
frutas.forEach((fruta, indice) => {
  console.log(`Índice ${indice}: ${fruta}`);
});

// Typed Array de números
const numeros = new Uint8Array([10, 20]);
for (const numero of numeros) {
  console.log(numero); // 10, 20
}
```

