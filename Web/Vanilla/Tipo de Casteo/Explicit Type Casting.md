Tipo de fundición significa transferir datos de un tipo de datos a otro especificando explícitamente el tipo para convertir los datos dados. La fundición de tipo explícito normalmente se realiza para que los datos compatibles con otras variables. Ejemplos de métodos de typecasting son `parseint()`, `parsefloat()`, `toString()`.


Una explicación mas sencillas es cuando **tú decides manualmente** convertir una "pera" en "manzana" (o viceversa), en lugar de dejar que JavaScript lo haga automáticamente.

Es como decirle a JavaScript: _"Oye, convierte esto en número/texto/booleano, por favor"_.

Es sumamente importante para evitar errores como estos

```js
// Sin Explicit Casting (puede fallar)
let manzanas = "5";
let peras = 3;
let total = manzanas + peras; // "53" (error si querías sumar)

// Con Explicit Casting (controlas el resultado)
let total = Number(manzanas) + peras; // 8 ✅
```

## Ejemplo: Convertir manzanas (string) a pera (número)

```js
let manzana = "15"; // 🍎 (string)
let pera = Number(manzana); // Convertimos EXPLÍCITAMENTE a número (🍐)

console.log(pera); // 15 (número)
console.log(typeof pera); // "number" ✅
```

**¿Qué se hizo?**
Usamos `Number()`, para transformar la pera (`15`) en una manzana (`15`).

## Ejemplo: Convertir pera (número) a manzana (string)

```js
let pera = 20; // 🍐 (número)
let manzana = String(pera); // Convertimos EXPLÍCITAMENTE a string (🍎)

console.log(manzana); // "20" (string)
console.log(typeof manzana); // "string" ✅
```

**¿Qué se hizo?**
Usamos `String()`, para transformar la pera (`20`) en una manzana (`20`).

## Ejemplo: Convertir a booleano (¿Es una fruta valida?)

```js
let manzana = ""; // 🍎 (string vacío, ¿manzana podrida?)
let pera = 0;     // 🍐 (número cero, ¿pera inexistente?)

console.log(Boolean(manzana)); // false (no es una manzana válida)
console.log(Boolean(pera));    // false (no es una pera válida)
console.log(Boolean("manzana")); // true (🍎 válida)
```

**Reglas clave**:
- **`false`**: `0`, `""`, `null`, `undefined`, `NaN`.
- **`true`**: Cualquier otro valor no vacío.
- De igual manera se puede revisar [[Type Conversion vs Coercion]] , donde se refiere mas a los tipos verdaderos y falsos.


## Ejemplo: Usando `parseInt` y `parseFloat` (para números)

```js
let manzanaConPera = "10peras"; // 🍎🍐 (string mezclado)
let peras = parseInt(manzanaConPera); // Extrae el número al inicio

console.log(peras); // 10 (número) 🍐
```

```js
let precioManzana = "9.99"; // 🍎 (string)
let precio = parseFloat(precioManzana); // Convierte a decimal

console.log(precio); // 9.99 (número) ✅
```

## Ejemplo: Usando operadores para conversion rápida

```js
// Convertir string a número con "+"
let manzana = "25"; // 🍎
let pera = +manzana; // "+" convierte EXPLÍCITAMENTE a número
console.log(pera); // 25 (🍐)

// Convertir número a booleano con "!!"
let pera = 0; // 🍐
console.log(!!pera); // false (0 es falsy)
```


## Tabla de métodos comunes de explicit casting

| Método              | Acción                        | Ejemplo                     |
| ------------------- | ----------------------------- | --------------------------- |
| `Number()`          | Convierte a número            | `Number("5") → 5`           |
| `String()`          | Convierte a string            | `String(5) → "5"`           |
| `Boolean()`         | Convierte a booleano          | `Boolean("hola") → true`    |
| `parseInt()`        | Convierte string a entero     | `parseInt("10px") → 10`     |
| `parseFloat()`      | Convierte string a decimal    | `parseFloat("9.99") → 9.99` |
| `+` operador unario | Convierte string a número     | `+"15" → 15`                |
| `!!`                | Convierte a booleano (truthy) | `!!"hola" → true`           |
