Un `Weak Set` es una colección de objetos que se comporta como un `Set` osea que solo puede haber una ocurrencia dentro del `Weak set`, ya que también es una colección única en palabras simples, tienes una cesta de frutas (objetos en JavaScript) y quieres recordar cuáles frutas ya has lavado. Pero no quieres modificar las frutas directamente, solo quieres mantener un registro de ellas.

En resumidas cuentas, Un **WeakSet** es como una lista especial donde puedes guardar objetos (como peras y manzanas) para recordar algo sobre ellos (por ejemplo, si ya los lavaste). Pero si ya no necesitas el objeto, el WeakSet automáticamente lo "borra" de la lista.

## Cual es su diferencia? 
**Con un array o un Set normal**: Podrías guardar las frutas en un array o un Set, pero eso mantendría una referencia fuerte a las frutas, lo que evitaría que el recolector de basura las elimine aunque ya no las necesites.

**Con un WeakSet**: Puedes usar un WeakSet para guardar las frutas lavadas sin preocuparte por la memoria, ya que no evita que las frutas sean eliminadas por el recolector de basura.

## Caracteristicas
Un **WeakSet** es una colección especial en JavaScript que solo puede contener objetos. Tiene dos características principales

**Solo permite objetos como elementos**. No puedes agregar números, strings, etc.

**No evita que los objetos sean eliminados por el recolector de basura**. Si un objeto ya no se usa en tu programa, el WeakSet automáticamente "olvida" ese objeto.


### Ejemplo

```js
// Crear un WeakSet
const frutasLavadas = new WeakSet();

// Crear algunas frutas (objetos)
const manzana = { nombre: "Manzana" };
const pera = { nombre: "Pera" };

// Agregar frutas lavadas al WeakSet
frutasLavadas.add(manzana);
frutasLavadas.add(pera);

// Verificar si una fruta está lavada
console.log(frutasLavadas.has(manzana)); // true
console.log(frutasLavadas.has(pera));    // true

// Si la manzana ya no se usa, el WeakSet la "olvida"
manzana = null;

// Ahora el WeakSet no tiene la manzana
console.log(frutasLavadas.has(manzana)); // false
```

## Porque usarlo?
- **No modifica el objeto original**: No agregas propiedades adicionales a la fruta.
- **Es eficiente con la memoria**: Si el objeto ya no se usa, el recolector de basura lo elimina y el WeakSet automáticamente lo "olvida".
- **Privacidad**: Los objetos en el WeakSet no son accesibles desde fuera, a menos que tengas una referencia a ellos.

