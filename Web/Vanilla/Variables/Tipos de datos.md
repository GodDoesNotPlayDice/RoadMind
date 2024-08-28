El tipo de datos se refiere al tipo de datos que puede contener una variable de JavaScript. Hay siete tipos de datos primitivos en **JavaScript (Número, BigInt, Cadena, Booleano, Nulo, Indefinido y Símbolo).** Los objetos no son primitivos.
# Tipos primitivos

## String
**String** es un tipo primitivo que contiene una secuencia de caracteres. La cadena en Javascript se escribe entre un par de comillas simples "o comillas dobles "". Ambas comillas se pueden usar para contener una cadena, pero solo si la comilla inicial es la misma que la comilla final.

## Number
**El tipo de datos Número en JavaScript representa números de punto flotante**, como 37 o -9,25. El constructor Number proporciona constantes y métodos para trabajar con números, y los valores de otros tipos se pueden convertir en números usando la función `Number()`.

```js
let num1 = 255; // integer
let num2 = 255.0; // floating-point number with no fractional part
let num3 = 0xff; // hexadecimal notation
let num4 = 0b11111111; // binary notation
let num5 = 0.255e3; // exponential notation

console.log(num1 === num2); // true
console.log(num1 === num3); // true
console.log(num1 === num4); // true
console.log(num1 === num5); // true
```

`255 y 255.0` son equivalentes, ya que JavaScript trata a ambos como el mismo número.  
`0xff` representa 255 en notación hexadecimal.  
`0b11111111` representa 255 en notación binaria.  
`0.255e3` es 255 en notación exponencial.  
Todas estas representaciones diferentes son **iguales** a 255 en JavaScript.

## Boolean
En JavaScript, un **booleano** es un tipo de datos simple que puede contener **uno** de **dos** valores: **verdadero** o **falso**. Estos valores se utilizan para representar **estados lógicos** y son esenciales para **controlar el flujo de un programa.**  
  
Los **booleanos** se usan comúnmente en declaraciones condicionales **(if, else, while, etc.)** para determinar si se debe ejecutar un bloque de código.

## BigInt
Un valor **BigInt**, también llamado a veces simplemente **BigInt**, es una primitiva `bigint`, creada agregando n al final de un literal entero, o llamando a la función `BigInt()` (sin el nuevo operador) y dándole un valor entero o cadena. valor.
```js
const previouslyMaxSafeInteger = 9007199254740991n;

const alsoHuge = BigInt(9007199254740991);
// 9007199254740991n

const hugeString = BigInt("9007199254740991");
// 9007199254740991n

const hugeHex = BigInt("0x1fffffffffffff");
// 9007199254740991n

const hugeOctal = BigInt("0o377777777777777777");
// 9007199254740991n

const hugeBin = BigInt(
  "0b11111111111111111111111111111111111111111111111111111",
);
// 9007199254740991n
```


## Undefined y Null

### Undefined
`undefined` es un tipo de datos **primitivo** en Javascript.  
Siempre que se declara una **variable pero no se inicializa ni se le asigna un valor**, se almacena como `undefined`. Una función devuelve indefinido si no se devolvió un valor. Un método o declaración también devuelve indefinido si la variable que se está evaluando no tiene un valor asignado.

### Null
El valor **nulo** en JavaScript significa la **ausencia deliberada de cualquier valor de objeto.** Se considera uno de los valores primitivos de JavaScript y un valor **falso**.

La **ausencia deliberada enfatiza el uso intencional de nulo** para indicar que una **variable no apunta a ningún objeto.** Esta declaración explícita transmite la naturaleza intencional de nulo, mostrando que la **variable debe estar vacía o inexistente en el momento de la ejecución.**


## Symbol
Los **símbolos** son un tipo de datos **primitivo único e inmutable en JavaScript**, introducido en ECMAScript 6 **(ES6)**. A menudo se utilizan para crear claves de **propiedad únicas** para objetos, lo que garantiza que **no se produzcan colisiones de claves de propiedad**. Cada valor de Símbolo es único, incluso si se crea con la misma descripción. Los símbolos se pueden crear usando la función `Symbol()`, y su caso de uso principal es agregar propiedades ocultas o especiales a objetos que no interfieran con otras propiedades o métodos.

```js
// Crear un símbolo
const mySymbol = Symbol('descripcion');

// Usar el símbolo como clave en un objeto
const myObject = {
  [mySymbol]: 'Valor asociado al símbolo'
};

// Acceder al valor usando el símbolo
console.log(myObject[mySymbol]); // Output: 'Valor asociado al símbolo'

```


**Utilidad**: `Symbol` se utiliza principalmente cuando necesitas garantizar la unicidad de las propiedades de un objeto o cuando trabajas con características avanzadas del lenguaje que requieren una personalización cuidadosa para evitar colisiones.

**Por ejemplo**:

- **Claves únicas en objetos:** Se usa `Symbol` para crear claves de propiedades en objetos que sean únicas y que no puedan ser sobrescritas accidentalmente por otras propiedades con el mismo nombre.
```js
const uniqueKey = Symbol('uniqueKey'); 
const obj = { [uniqueKey]: 'Este valor es único' };
```

- **Implementación de características privadas:** Aunque no existen propiedades privadas en JavaScript nativo, `Symbol` puede actuar como una forma de crear propiedades que no sean accesibles de manera accidental, ya que no pueden ser iteradas con `for...in` o enumeradas con `Object.keys()`.

```js
const hiddenProperty = Symbol('hidden');
const obj = {
  [hiddenProperty]: 'Valor oculto'
};
```

- **Evitar colisiones en extensiones de objetos:** Cuando se extiende un objeto, especialmente en entornos donde múltiples bibliotecas o módulos puedan interactuar con el mismo objeto, `Symbol` asegura que las propiedades agregadas no colisionen con otras propiedades.

```js
const uniqueMethod = Symbol('uniqueMethod');
Array.prototype[uniqueMethod] = function () {
  return 'Método único para arrays';
};
```

- **Metaprogramación**: Los símbolos también son útiles en metaprogramación, especialmente con los métodos simbólicos que JavaScript proporciona, como `Symbol.iterator`, `Symbol.toPrimitive`, `Symbol.toStringTag`, entre otros, que permiten personalizar comportamientos de objetos.

```js
const obj = {
  [Symbol.iterator]: function* () {
    yield 1;
    yield 2;
    yield 3;
  }
};

for (let value of obj) {
  console.log(value); // 1, 2, 3
}

```



# Tipos no primitivos
## Objects
El objeto JavaScript es una estructura de datos que nos permite tener pares **clave-valor**.

Entonces podemos **tener claves distintas** y cada clave se asigna a un valor que puede ser de cualquier tipo de datos JavaScript. **Comparándolo con un objeto del mundo real, un bolígrafo es un objeto con varias propiedades como color, diseño, material del que está hecho, etc.** De la misma manera, los objetos **JavaScript pueden tener propiedades que definen sus características.**

Se puede crear un objeto con corchetes `{…}` con una lista opcional de propiedades. Una propiedad es un par `“clave: valor”`, donde clave es una cadena (**también llamada “nombre de propiedad”)** y el valor puede ser cualquier cosa.

```javascript
let user = new Object(); // "object constructor" syntax
let user = {};  // "object literal" syntax
```

Los objetos como bien sabemos son un tipo de dato que nos permite almacenar diferentes **tipos de datos, como números, cadenas, booleanos, funciones, arreglos, etc.**  
```javascript
let user = {     // an object
  name: "John",  // by key "name" store value "John"
  age: 30        // by key "age" store value 30
};
```

```javascript
// get property values of the object:
alert( user.name ); // John
alert( user.age ); // 30
```

El valor puede ser de cualquier tipo. Agreguemos uno booleano

```javascript
user.isAdmin = true;
```

Para eliminar una propiedad, se puede utilizar la palabra clave `delete`.

```javascript
delete user.age;
```

También podemos usar nombres de propiedades de varias palabras, pero luego deben ir entre comillas, no creo que sea tan buena práctica.

```javascript
let user = {
  name: "John",
  age: 30,
  "likes birds": true  // multiword property name must be quoted
};
```

La última propiedad de la lista puede terminar con una coma.
Esto se llama coma "**trailing**" o "**hanging**". Hace que sea más fácil agregar/eliminar/mover propiedades, porque todas las líneas se vuelven iguales.

```javascript
let user = {
  name: "John",
  age: 30,
}
```

Mas de los [[Objetos]].

## Type of Operator
Puede utilizar el operador **typeOf** para encontrar el tipo de datos de una variable de JavaScript. Devuelve una cadena que indica el tipo de valor del operando proporcionado.

La sintaxis es la siguiente:
```javascript
typeof operand
```

### Descripciones de los tipos de datos

| Type                                                                                              | Result              |
| ------------------------------------------------------------------------------------------------- | ------------------- |
| [Undefined](#undefined)                                                                           | `"undefined"`       |
| [Null](#Null)                                                                                     | `"object"` (reason) |
| [Boolean](#Boolean)                                                                               | `"boolean"`         |
| [Number](#Number)                                                                                 | `"number"`          |
| [BigInt](#Bigint)                                                                                 | `"bigint"`          |
| [String](#String)                                                                                 | `"string"`          |
| [Symbol](#Symbol)                                                                                 | `"symbol"`          |
| [Function](#function) (implements [[Call]] in ECMA-262 terms; [classes](#) are functions as well) | `"function"`        |
| Any other object                                                                                  | `"object"`          |

### Ejemplo de los tipos de datos
```javascript
// Numbers
typeof 37 === "number";
typeof 3.14 === "number";
typeof 42 === "number";
typeof Math.LN2 === "number";
typeof Infinity === "number";
typeof NaN === "number"; // Despite being "Not-A-Number"
typeof Number("1") === "number"; // Number tries to parse things into numbers
typeof Number("shoe") === "number"; // including values that cannot be type coerced to a number

typeof 42n === "bigint";

// Strings
typeof "" === "string";
typeof "bla" === "string";
typeof `template literal` === "string";
typeof "1" === "string"; // note that a number within a string is still typeof string
typeof typeof 1 === "string"; // typeof always returns a string
typeof String(1) === "string"; // String converts anything into a string, safer than toString

// Booleans
typeof true === "boolean";
typeof false === "boolean";
typeof Boolean(1) === "boolean"; // Boolean() will convert values based on if they're truthy or falsy
typeof !!1 === "boolean"; // two calls of the ! (logical NOT) operator are equivalent to Boolean()

// Symbols
typeof Symbol() === "symbol";
typeof Symbol("foo") === "symbol";
typeof Symbol.iterator === "symbol";

// Undefined
typeof undefined === "undefined";
typeof declaredButUndefinedVariable === "undefined";
typeof undeclaredVariable === "undefined";

// Objects
typeof { a: 1 } === "object";

// use Array.isArray or Object.prototype.toString.call
// to differentiate regular objects from arrays
typeof [1, 2, 4] === "object";

typeof neconsole.log(typeof 42);
// Expected output: "number"

console.log(typeof 'blubber');
// Expected output: "string"

console.log(typeof true);
// Expected output: "boolean"

console.log(typeof undeclaredVariable);
// Expected output: "undefined"w Date() === "object";
typeof /regex/ === "object";

// The following are confusing, dangerous, and wasteful. Avoid them.
typeof new Boolean(true) === "object";
typeof new Number(1) === "object";
typeof new String("abc") === "object";

// Functions
typeof function () {} === "function";
typeof class C {} === "function";
typeof Math.sin === "function";
```


**Type of** de null
```javascript
// This stands since the beginning of JavaScript
typeof null === "object";
```

En la primera implementación de JavaScript, los valores de JavaScript se representaban como una etiqueta de tipo y un valor. La etiqueta de **tipo para los objetos era 0**. null se representaba como el puntero NULL (**0x00** en la mayoría de las plataformas). En consecuencia, null tenía 0 como etiqueta de tipo, de ahí el valor de retorno del tipo "objeto".

En simples palabras se puede decir

En la primera implementación de JavaScript, cada valor se representaba con un "tipo" y un "valor". El "tipo" es como una etiqueta que indica qué clase de dato es **(por ejemplo, un número, un texto, un objeto, etc.).**

Para los objetos, la etiqueta de tipo era 0. Además, el valor especial `null` (que significa que algo no tiene ningún valor o está vacío) se representaba con un puntero NULL, que es 0 en la mayoría de las plataformas.

Como tanto los objetos como `null` tenían la etiqueta de tipo 0, JavaScript pensaba que `null` era un objeto cuando se le preguntaba de qué tipo era (`typeof null`). Por eso, al usar `typeof null`, JavaScript devolvía "object", aunque `null` no sea realmente un objeto. Este es un comportamiento que quedó en JavaScript debido a esa primera implementación.

```js

console.log(typeof null === "null")
// false
console.log(typeof null)
// Expected output: "object"
```

En resumen es todo un caso lo del null [[Problema del Null]]

### New operator
Todas las funciones constructoras llamadas con **new** devolverán elementos no primitivos **("objeto" o "función")**. La mayoría devuelve objetos.!
```js
const str = new String("String");
const num = new Number(100);

typeof str; // "object"
typeof num; // "object"

const func = new Function();

typeof func; // "function"
```

El operador **typeof** tiene mayor prioridad que los **operadores binarios como la suma** (+). Por lo tanto, se necesitan paréntesis **para evaluar el tipo de resultado de una suma.**
```js
// Parentheses can be used for determining the data type of expressions.
const someData = 99;

console.log(typeof someData + " Wisen"); // "number Wisen"
console.log(typeof (someData + " Wisen")) // "string"
```

Por lo general, siempre se garantiza que `typeof` devolverá una cadena para cualquier operando que se le proporcione. Incluso con identificadores no declarados, `typeof` devolverá `undefined` en lugar de generar un error.

```js
typeof undeclaredVariable; // "undefined"
```

