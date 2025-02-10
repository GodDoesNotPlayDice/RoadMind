`Map` es una colección de pares clave-valor donde las claves pueden ser de cualquier tipo, a diferencia de los objetos donde las claves deben ser cadenas (strings) o símbolos (symbols). `Map` es una estructura de datos muy útil cuando necesitas almacenar y manipular datos en pares clave-valor, especialmente cuando las claves no son cadenas.

## Creando y Usando un map

### Crear un map
Puedes crear un `Map` vacío o inicializarlo con un conjunto de pares clave-valor.

```js
// Crear un Map vacío
let mapa = new Map();

// Crear un Map con valores iniciales
let mapaInicializado = new Map([
  ['clave1', 'valor1'],
  ['clave2', 'valor2']
]);
```

### Métodos principales

**`set(clave, valor)`**: Añade un nuevo par clave-valor al `Map`.

```js
mapa.set('clave3', 'valor3');
```

**`get(clave)`**: Obtiene el valor asociado a una clave. Si la clave no existe, devuelve `undefined`.

```js
console.log(mapa.get('clave3')); // 'valor3'
```

**`has(clave)`**: Verifica si una clave existe en el `Map`. Devuelve `true` o `false`.

```js
console.log(mapa.has('clave3')); // true
```

**`delete(clave)`**: Elimina un par clave-valor del `Map` usando la clave. Devuelve `true` si la clave existía y fue eliminada, `false` en caso contrario.

```js
mapa.delete('clave3');!
```

**`clear()`**: Elimina todos los pares clave-valor del `Map`.

```js
mapa.clear();
```

**`size`**: Propiedad que devuelve el número de pares clave-valor en el `Map`.

```js
console.log(mapa.size); // 0
```


### Iterar sobre un map
Puedes iterar sobre un `Map` de varias maneras:

**`forEach`**: Itera sobre cada par clave-valor.

```js
mapaInicializado.forEach((valor, clave) => {
  console.log(`${clave}: ${valor}`);
});
```

**`for...of`**: Itera sobre los pares clave-valor usando un bucle `for...of`.

```js
mapaInicializado.forEach((valor, clave) => {
  console.log(`${clave}: ${valor}`);
});
```

**`keys()`**: Devuelve un iterador con las claves del `Map`.

```js
for (let clave of mapaInicializado.keys()) {
  console.log(clave);
}
```

**`values()`**: Devuelve un iterador con los valores del `Map`.

```js
for (let valor of mapaInicializado.values()) {
  console.log(valor);
}
```

**`entries()`**: Devuelve un iterador con los pares clave-valor (es el método por defecto cuando se itera directamente sobre el `Map`).

```js
for (let [clave, valor] of mapaInicializado.entries()) {
  console.log(`${clave}: ${valor}`);
}
```


### Ejemplo completo

```js
let mapa = new Map();

mapa.set('nombre', 'Juan');
mapa.set('edad', 30);
mapa.set('esEstudiante', false);

console.log(mapa.get('nombre')); // 'Juan'
console.log(mapa.has('edad')); // true
console.log(mapa.size); // 3

mapa.delete('esEstudiante');
console.log(mapa.size); // 2

for (let [clave, valor] of mapa) {
  console.log(`${clave}: ${valor}`);
}

mapa.clear();
console.log(mapa.size); // 0
```