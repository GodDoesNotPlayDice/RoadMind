La conversión de tipo implícito ocurre cuando el compilador o el tiempo de ejecución convierten automáticamente los tipos de datos. JavaScript es un lenguaje tipado libremente y la mayoría de las veces los operadores convierten automáticamente un valor al tipo correcto.

Una explicación mas fácil seria.

Imagina que tienes una caja de **peras** (números) y una caja de **manzanas** (textos o strings).  
JavaScript.

JavaScript, a veces, intenta "convertir" peras en manzanas (o viceversa) automáticamente para realizar operaciones. Esto es **Implicit Type Casting**.

`+` : favorece strings (concatena)
`-`, `*`, `/`: favorece números
`==` vs `===` : usar siempre usar la validación estricta para evitar sorpresas.
## Ejemplo de sumas peras y manzanas

```js
let peras = 5;    // Número (🍐)
let manzanas = "3"; // String (🍎)

let resultado = peras + manzanas; // 🤔
console.log(resultado); // "53" (string)
```

**¿Que es lo que paso?**, lo que paso fue.
- JavaScript convirtió la **pera** (`5`) en una **manzana** (`"5"`) para poder concatenar (unir textos).
- Resultado: `"5" + "3" = "53"` (una manzana gigante con el texto "53").

## Ejemplo cuando restas manzanas y peras

```js
let manzanas = "10"; // String (🍎)
let peras = 3;       // Número (🍐)

let resultado = manzanas - peras; // 🤔
console.log(resultado); // 7 (número)
```

**¿Que es lo que paso?**, lo que paso fue.
- JavaScript convirtió la **manzana** (`"10"`) en una **pera** (`10`) para poder restar.
- Resultado: `10 - 3 = 7` (una pera normal).

## Ejemplo comparando manzanas

```js
console.log(5 == "5");  // true  😱
console.log(5 === "5"); // false ✅
```

#### **`==` (Loose Equality)**:
- Convierte la manzana (`"5"`) en pera (`5`) y compara valores. 
	- Resultado: `5 == 5` → `true`.
#### **`===` (Strict Equality)**:
- No hace conversión. Compara **tipo y valor**.  
	- Resultado: `5 (número) !== "5" (string)` → `false`.

## Casos Raros!
JavaScript a veces toma decisiones... cuestionables:

```js
console.log([] + []);        // "" (string vacío)
console.log([] + {});        // "[object Object]"
console.log("abc" - 5);      // NaN (Not a Number)
console.log(true + 1);       // 2 (true es 1)
console.log(false + "manzana"); // "falsemanzana"
```

