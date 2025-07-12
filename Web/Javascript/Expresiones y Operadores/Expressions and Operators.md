Las expresiones y los operadores son fundamentales para realizar operaciones y manipular datos, a continuación sigue [[Web/Javascript/Funciones/Funciones]]

## Operadores aritméticos
- `+` (Suma)
- `-` (Resta)
- `*` (Multiplicación)
- `/` (División)
- `%` (Módulo, resto de la división)
- `**` (Exponenciación)

```js
let suma = 5 + 3; // 8
let resta = 10 - 4; // 6
let multiplicacion = 2 * 3; // 6
let division = 10 / 2; // 5
let modulo = 10 % 3; // 1
let exponente = 2 ** 3; // 8
```

## Operadores de Comparación
Estos operadores también son tratados en [[Sentencias condicionales]]
- `==` (Igualdad, sin tipo)
- `===` (Igualdad estricta, con tipo)
- `!=` (Desigualdad, sin tipo)
- `!==` (Desigualdad estricta, con tipo)
- `>` (Mayor que)
- `<` (Menor que)
- `>=` (Mayor o igual que)
- `<=` (Menor o igual que)

```js
let a = 5;
let b = "5";
console.log(a == b); // true
console.log(a === b); // false
console.log(a > 4); // true
```

## Operadores lógicos
- `&&` (AND lógico)
- `||` (OR lógico)
- `!` (NOT lógico)

```js
let x = true;
let y = false;
console.log(x && y); // false
console.log(x || y); // true
console.log(!x); // false
```

## Operadores de asignación
- `=` (Asignación)
- `+=` (Suma y asignación)
- `-=` (Resta y asignación)
- `*=` (Multiplicación y asignación)
- `/=` (División y asignación)
- `%=` (Módulo y asignación)
- `**=` (Exponenciación y asignación)

```js
let z = 10;
z += 5; // z = z + 5 → 15
z *= 2; // z = z * 2 → 30
```

## Operadores Unarios
- `++` (Incremento)
- `--` (Decremento)
- `+` (Positivo)
- `-` (Negativo)
- `!` (NOT lógico)

```js
let contador = 0;
contador++; // contador = 1
contador--; // contador = 0
let num = -5;
let positivo = +num; // -5
let negativo = -num; // 5
```

## Operador de cadena (string)
`+` (Concatenación)

```js
let saludo = "Hola, " + "mundo!"; // "Hola, mundo!"
```

## Operadores de bits
- `&` (AND a nivel de bits)
- `|` (OR a nivel de bits)
- `^` (XOR a nivel de bits)
- `~` (NOT a nivel de bits)
- `<<` (Desplazamiento a la izquierda)
- `>>` (Desplazamiento a la derecha)
- `>>>` (Desplazamiento a la derecha sin signo)

```js
let a = 5; // 0101 en binario
let b = 3; // 0011 en binario
console.log(a & b); // 0001 → 1
console.log(a | b); // 0111 → 7
```

### AND a nivel de bits`&`
Compara cada bit de dos números y devuelve `1` si ambos bits son `1`, de lo contrario, devuelve `0`.

```js
let a = 5;    // 0101 en binario
let b = 3;    // 0011 en binario
let resultado = a & b; // 0001 → 1
console.log(resultado); // 1
```

### OR a nivel de bits `|`
Compara cada bit de dos números y devuelve `1` si al menos uno de los bits es `1`.

```js
let a = 5;    // 0101 en binario
let b = 3;    // 0011 en binario
let resultado = a | b; // 0111 → 7
console.log(resultado); // 7
```

### XOR a nivel de bits `^`
Compara cada bit de dos números y devuelve `1` si los bits son diferentes, de lo contrario, devuelve `0`.

```js
let a = 5;    // 0101 en binario
let b = 3;    // 0011 en binario
let resultado = a ^ b; // 0110 → 6
console.log(resultado); // 6
```

### NOT a nivel de bits `~`
Invierte todos los bits de un número. Es decir, convierte `0` en `1` y `1` en `0`.

```js
let a = 5;    // 0101 en binario
let resultado = ~a; // 1010 → -6 (en complemento a 2)
console.log(resultado); // -6
```


### Desplazamiento a la izquierda `<<`
Desplaza los bits de un número hacia la izquierda y rellena con `0` a la derecha.
```js
let a = 5;    // 0101 en binario
let resultado = a << 1; // 1010 → 10
console.log(resultado); // 10
```

### Desplazamiento a la derecha `>>`
Desplaza los bits de un número hacia la derecha, manteniendo el signo (el bit más a la izquierda).

```js
let a = -16;    // 11110000 en binario (en complemento a 2)
let resultado = a >> 2; // 11111100 → -4
console.log(resultado); // -4
```

### Desplazamiento a la derecha rellenando un 0 `>>>`

Desplaza los bits de un número hacia la derecha, rellenando con `0` a la izquierda (ignora el signo).

```js
let a = -16;    // 11110000 en binario (en complemento a 2)
let resultado = a >>> 2; // 00111100 → 60
console.log(resultado); // 60
```

## Operador condicional (Ternario)
`condición ? expr1 : expr2`

```js
let edad = 18;
let mensaje = edad >= 18 ? "Mayor de edad" : "Menor de edad";
console.log(mensaje); // "Mayor de edad" true : false
```

## Operador coma
`,` Es un operador poco común pero útil en ciertos contextos. Su función principal es permitirte evaluar múltiples expresiones en una sola declaración, devolviendo el valor de la última expresión. Aquí te explico mejor para qué puede servir y cómo se usa:

### Ejemplo multiple declaración
- El operador coma te permite evaluar varias expresiones en una sola línea, pero solo el valor de la última expresión es devuelto.
- Esto puede ser útil cuando quieres ejecutar varias operaciones en una sola declaración, como en bucles o en la inicialización de variables

**Ejemplo**
En este caso, se evalúan las expresiones `1`, `2` y `3`, pero solo el valor de la última expresión (`3`) se asigna a `a`.

```js
let a = (1, 2, 3); // a = 3

console.log(a) // 3
```


### Ejemplo en bucles `for`:
El operador coma es útil en bucles `for` cuando necesitas inicializar o actualizar múltiples variables.

**Ejemplo**
Aquí, el operador coma se usa para inicializar `i` y `j` al mismo tiempo, y también para incrementar `i` y decrementar `j` en cada iteración.

```js
for (let i = 0, j = 10; i < 10; i++, j--) {
    console.log(`i: ${i}, j: ${j}`);
}
```




## BigInt Operator
Los operadores **BigInt** se utilizan para trabajar con números enteros grandes que no pueden ser representados con el tipo de dato `Number`. En JavaScript, los números tienen un límite de precisión (hasta `2^53 - 1`), pero con `BigInt`, puedes manejar números mucho más grandes.


### Creación de un BigInt
Para crear un `BigInt`, añades una `n` al final del número o usas la función `BigInt()`.

```js
let bigNum = 123456789012345678901234567890n;
let bigNum2 = BigInt("123456789012345678901234567890");
```

### Operadores con BigInt
Los operadores que funcionan con `Number` también funcionan con `BigInt`, excepto el operador de división (`/`), que redondea hacia cero en `BigInt`

- `+` (Suma)
- `-` (Resta)
- `*` (Multiplicación)
- `/` (División, redondea hacia cero)
- `%` (Módulo)
- `**` (Exponenciación)

#### Suma y Multiplicación
```js
let a = 123456789012345678901234567890n;
let b = 987654321098765432109876543210n;
let suma = a + b;
let multiplicacion = a * b;
console.log(suma); // 1111111110111111111011111111100n
console.log(multiplicacion); // 121932631137021795226185032733622923332237463801111263526900n
```

#### División (Redondeada hacia cero)
```js
let a = 10n;
let b = 3n;
let division = a / b; // 3n (redondea hacia cero)
console.log(division); // 3n
```


#### Modulo (Resto de la division)
```js
let a = 10n;
let b = 3n;
let modulo = a % b; // 1n
console.log(modulo); // 1n
```

### Consideraciones

#### Mesclar BigInt con Number
No puedes mezclar directamente `BigInt` con `Number` en operaciones. Debes convertir uno de ellos al tipo del otro.

```js
let a = 10n;
let b = 5;
// Esto dará un error:
// let resultado = a + b;
// Solución:
let resultado = a + BigInt(b); // 15n
```

#### Precision Infinita
`BigInt` no tiene límite de tamaño, pero consume más memoria que `Number`.

#### No usar con métodos que esperan `Number`
Algunos métodos, como `Math.sqrt()`, no funcionan con `BigInt`.