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