## Que es un weak map con peras y manzanas
Imagina que tienes una cesta de frutas (un `WeakMap`). En esta cesta, puedes guardar pares de frutas y etiquetas. 

Por ejemplo, puedes poner una manzana con una etiqueta que diga "roja" y una pera con una etiqueta que diga "verde".

## Características clave de un `WeakMap`:

**Solo objetos como claves**: En nuestra cesta de frutas, solo puedes usar frutas (objetos) como claves. No puedes usar una etiqueta directamente como clave, solo frutas.

**Referencias débiles**: Si decides que ya no quieres una fruta y la tiras a la basura (es decir, el objeto ya no se usa en tu programa), la etiqueta asociada a esa fruta también desaparece automáticamente de la cesta. Esto es útil para no acumular cosas que ya no necesitas.

**No es iterable**: No puedes mirar todas las frutas y etiquetas de la cesta de una vez. Solo puedes preguntar por una fruta específica y ver si tiene una etiqueta.

```js
// Crear un WeakMap (nuestra cesta de frutas)
let cesta = new WeakMap();

// Crear algunas frutas (objetos)
let manzana = { nombre: "Manzana" };
let pera = { nombre: "Pera" };

// Asignar etiquetas a las frutas
cesta.set(manzana, "roja");
cesta.set(pera, "verde");

// Ver las etiquetas
console.log(cesta.get(manzana)); // "roja"
console.log(cesta.get(pera));    // "verde"

// Si decides que ya no quieres la manzana
manzana = null;

// La etiqueta de la manzana desaparece automáticamente de la cesta
// porque la referencia a la manzana se ha perdido.
```


