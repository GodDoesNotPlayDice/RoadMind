Se refiere a la conversión de un tipo de dato a otro. Esto puede ocurrir de manera explícita (cuando tú decides convertir un tipo de dato) o implícita (cuando JavaScript lo hace automáticamente en ciertas situaciones).

## Conversion Explicita
Aquí tú decides convertir un tipo de dato a otro usando funciones o métodos específicos.

### Convertir string
convertir un valor a una cadena de texto usando `String()` o el método `.toString()`.

```js
let numero = 42;
let texto = String(numero); // "42"
let otroTexto = numero.toString(); // "42"

console.log(typeof texto); // "string"
```

### Convertir a Numero
Puedes convertir un valor a un número usando `Number()`, `parseInt()`, o `parseFloat()`.

```js
let texto = "123";
let numero = Number(texto); // 123
let decimal = parseFloat("3.14"); // 3.14
let entero = parseInt("10.9"); // 10 (solo toma la parte entera)

console.log(typeof numero); // "number"
```


### Convertir a Booleano
Puedes convertir un valor a booleano usando `Boolean()`.

```js
let valor1 = Boolean(1); // true
let valor2 = Boolean(0); // false
let valor3 = Boolean("Hola"); // true
let valor4 = Boolean(""); // false

console.log(typeof valor1); // "boolean"
```

## Conversion Implícita (Coerción)
JavaScript convierte automáticamente los tipos de datos en ciertas situaciones, como en operaciones o comparaciones.

### Coerción en operaciones
Cuando usas operadores como `+`, `-`, `*`, `/`, JavaScript puede convertir tipos automáticamente.

```js
let numero = 10;
let texto = "5";

let resultado1 = numero + texto; // "105" (concatena como string)
let resultado2 = numero - texto; // 5 (convierte "5" a número)
let resultado3 = numero * texto; // 50 (convierte "5" a número)
let resultado4 = numero / texto; // 2 (convierte "5" a número)
```

### Coerción en comparaciones
En comparaciones con `==`, JavaScript intenta convertir los tipos para comparar valores.

```js
console.log(5 == "5"); // true (convierte el string "5" a número)
console.log(0 == false); // true (convierte false a 0)
console.log("" == false); // true (convierte ambos a 0)
```

Para evitar la coerción en comparaciones, usa `===` (igualdad estricta), que no convierte tipos.

```js
console.log(5 === "5"); // false (no convierte tipos)
console.log(0 === false); // false (no convierte tipos)
```

### Coerción en Contextos Booleanos
En contextos donde se espera un booleano (como en `if`, `while`, etc.), JavaScript convierte automáticamente.

```js
if ("Hola") {
  console.log("Esto se ejecuta"); // "Hola" es truthy
}

if (0) {
  console.log("Esto no se ejecuta"); // 0 es falsy
}
```

## Valores Truthy y Falsy
En JavaScript, algunos valores se consideran **falsy** (equivalen a `false` en un contexto booleano) y otros **truthy** (equivalen a `true`).

### Valores Falsy:
**False**, **0**, **""**, **null**, **undefined**, **Nan**

### Valores Truthy
**Hola**, **42**, **[]**, **{}**, **true**


