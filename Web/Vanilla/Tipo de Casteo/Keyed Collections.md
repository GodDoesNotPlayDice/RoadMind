Las Keyed collection son colecciones de datas ordenadas por una key no por un index, estos son asociativos por naturaleza, ejemplos de estos son **map y set objects**, son iterables en el orden de inserción.

El problema que este busca resolver es el siguiente, una keyed collection busca solucionar
1) Guardar cosas con un identificador único y flexible
2) Evita duplicados en listas
3) Claves tanto texto como numéricas
4) Mantiene un orden de inserción
5) Mantiene métodos prácticos para manipular datos

## Ejemplo sin y con keyed collection.

### Problema 1
Quiero guardar cosas con identificadores únicos y flexibles, las solución es usar un **map** o **object**
- Si usas un array tradicional, solo puedes acceder desde una posición numérica.`frutas[0]` 
- Con **claves**, accedes directamente por un identificador único. `frutas.get("manzanas")` o `frutas.manzana`

**Sin keyed collection**
```js
// Sin clave: ¿Cómo diferenciar una fruta de otra?
let frutas = ["🍎", "🍐", "🍌"];
console.log(frutas[0]); // "🍎", pero... ¿qué fruta es? No es intuitivo.
```

**Con keyed collection**
```js
let frutasMap = new Map();
frutasMap.set("manzana", "🍎");
frutasMap.set("pera", "🍐");

console.log(frutasMap.get("manzana")); // "🍎" → ¡Clave descriptiva!
```

### Problema 2
Evitar la duplicación en la lista, la solución a este problema es usar un **set**.
- Si usas un array normal, tendrías que verificar manualmente si un elemento ya existe.
- El **set** lo hace automáticamente.


**Sin keyed collection**
```js
let frutas = ["🍎", "🍐", "🍎"];
// Verificar si ya existe antes de añadir:
if (!frutas.includes("🍎")) {
  frutas.push("🍎");
}
// ¡Engorroso!
```

**Con keyed collection**
```js
let frutasUnicas = new Set();
frutasUnicas.add("🍎");
frutasUnicas.add("🍐");
frutasUnicas.add("🍎"); // ¡Ignora el duplicado automáticamente!
console.log(frutasUnicas); // {"🍎", "🍐"}
```

### Problema 3
Querer que las claves no sean solo texto refiere a que en un objeto tradicional las claves siempre son strings o símbolos, pero usando **map** es posible usar **obj, números, funciones..** como claves.

**Sin keyed collection**
```js
let objeto = { 1: "🍎", true: "🍐" };
console.log(objeto["1"]); // "🍎" → JavaScript convierte la clave 1 a string.
```

**Con keyed collection**
```js
let mapa = new Map();
const clavePersonalizada = { tipo: "fruta" };

mapa.set(clavePersonalizada, "🍌");
mapa.set(100, "🍊");

console.log(mapa.get(clavePersonalizada)); // "🍌" → ¡Clave compleja!
```

### Problema 4
Necesidad de mantener el orden de inserción, la solución a este problema esta en **Map**, esto ocurre ya que en los objetos antiguos el orden de las claves no era predecible. (internet vieja)

```js
let mapaOrdenado = new Map();
mapaOrdenado.set("z", "🍎");
mapaOrdenado.set("a", "🍐");

// Recorrer en orden de inserción:
mapaOrdenado.forEach((valor, clave) => {
  console.log(clave, valor); // Primero "z", luego "a".
});
```

### Problema 5
Querer que métodos prácticos para su manipulación, la solución para este problema es usar **Map** y **Set**, que tienen métodos como **.has()**, **.delete()**, **.size**, etc

```js
let inventario = new Map();
inventario.set("manzanas", 10);
inventario.set("peras", 5);

// Verificar existencia:
console.log(inventario.has("manzanas")); // true

// Eliminar:
inventario.delete("peras");

// Tamaño actual:
console.log(inventario.size); // 1
```

Conoce los tipos de Keyed Collections [[Web/Vanilla/Tipo de Casteo/Map|Map]], [[Weak Map]], [[Set]], [[Weak Set]]