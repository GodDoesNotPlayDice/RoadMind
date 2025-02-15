Los operadores de comparación se utilizan en **declaraciones** lógicas para determinar la **igualdad** o la **diferencia** entre variables o valores. 

Los operadores de comparación se pueden usar en declaraciones condicionales para **comparar** valores y tomar **medidas** según el resultado.


Para empezar, en Javascript existen dos tipos de comparaciones de igualdad:
1. **Igualdad débil**: `==`
2. **Igualdad estricta**: `===`

## Igualdad débil `==`
La igualdad débil solo compara **el valor**, pero no el tipo de dato. Si los tipos son diferentes, JavaScript intenta convertirlos a un mismo tipo antes de comparar.

```js
let peras = 2;       // Número
let manzanas = "2";  // String

console.log(peras == manzanas); // true
```

### ¿Que es lo que pasó?
Paso que `peras` es un numero (`2`) y `manzanas` es un string (`"2"`), Javascript en este tipo de comparaciones débiles hace conversiones de los tipos mas explicado en [[Type Conversion vs Coercion]] donde una vez convertidos ambos a `int` da un `true`

## Igualdad estricta `===`
La igualdad estricta compara **tanto el valor como el tipo de dato**. Si los tipos son diferentes, directamente devuelve `false`.

```js
let peras = 2;       // Número
let manzanas = "2";  // String

console.log(peras === manzanas); // false
```

En este caso si es devuelto un `false` ya que si esta validando los tipos.


## Comparación con objetos
Si comparas objetos (como un cesto de peras y un cesto de manzanas), JavaScript solo devuelve `true` si ambos son **el mismo objeto en memoria**.

```js
let cestoDePeras = { fruta: "pera" };
let otroCestoDePeras = { fruta: "pera" };

console.log(cestoDePeras == otroCestoDePeras);  // false
console.log(cestoDePeras === otroCestoDePeras); // false

let mismoCesto = cestoDePeras;
console.log(cestoDePeras === mismoCesto); // true
```

### ¿Que es lo que pasó?
Aunque ambos cestos tienen la misma fruta, son objetos diferentes en memoria, en cambio, Solo `mismoCesto` es igual a `cestoDePeras` porque apuntan al mismo objeto.


## Object.is

`Object.is` es un método en JavaScript que compara dos valores de manera **estricta**, similar a `===`, pero con algunas diferencias clave. Es especialmente útil para casos especiales como `NaN` y `-0`.

```js
let peras = 2;       // Número
let manzanas = "2";  // String

console.log(Object.is(peras, manzanas)); // false
```

### Diferencia
La diferencia recae en  dos casos especiales donde `Object.is` se comporta diferente a `===`:

#### Comparaciones NaN

```js
console.log(Object.is(NaN, NaN)); // true
console.log(NaN === NaN);        // false
```

#### Comparaciones -0 y 0

```js
console.log(Object.is(-0, 0)); // false
console.log(-0 === 0);         // true
```


| Comparación   | `2 == "2"`   | `2 === "2"`   | `Object.is(2, "2")`   |
| ------------- | ------------ | ------------- | --------------------- |
| **Resultado** | `true`       | `false`       | `false`               |
| Comparación   | `NaN == NaN` | `NaN === NaN` | `Object.is(NaN, NaN)` |
| **Resultado** | `false`      | `false`       | `true`                |
| Comparación   | `-0 == 0`    | `-0 === 0`    | `Object.is(-0, 0)`    |
| **Resultado** | `true`       | `true`        | `false`               |
