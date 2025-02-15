# Square Brackets
Los atributos **multi-word** no pueden ser llamados por punto.

Los corchetes son mucho más poderosos que la notación de puntos. Permiten cualquier nombre de propiedad y variable. Pero también son más complicados de escribir.  
  
Entonces, la mayoría de las veces, cuando los nombres de las propiedades son conocidos y simples, se usa el punto. Y si necesitamos algo más complejo, cambiamos a corchetes.

```javascript
// this would give a syntax error
user.likes birds = true
```

El punto requiere que la clave sea un identificador de variable válido. Eso implica: no contiene espacios, no comienza con un dígito y no incluye caracteres especiales (`$` y `_` están permitidos).

Aquí hay una “Square Brackets Notation” alternativa que funciona con cualquier cadena.

```javascript
let user = {};

// set
user["likes birds"] = true;

// get
alert(user["likes birds"]); // true

// delete
delete user["likes birds"];
```

Los corchetes también proporcionan una forma de obtener el nombre de la propiedad como resultado de cualquier expresión **(a diferencia de una cadena literal)**, como a partir de una variable, como se muestra a continuación:

```javascript
let key = "likes birds";

// same as user["likes birds"] = true;
user[key] = true;
```

Aquí, la clave variable puede **calcularse en tiempo de ejecución o depender de la entrada del usuario.** Y luego lo usamos para acceder a la propiedad. Eso nos da una gran flexibilidad.

```javascript
let user = {
  name: "John",
  age: 30
};

let key = prompt("What do you want to know about the user?", "name");

// access by variable
alert( user[key] ); // John (if enter "name")
```

La notación de puntos no se puede utilizar de manera similar.

```javascript
let user = {
  name: "John",
  age: 30
};

let key = "name";
alert( user.key ) // undefined
```



## Computed properties
Podemos usar corchetes en un objeto literal al crear un objeto. Eso se llama "computed properties"

```javascript
let fruit = prompt("Which fruit to buy?", "apple");

let bag = {
  [fruit]: 5, // the name of the property is taken from the variable fruit
};

alert( bag.apple ); // 5 if fruit="apple"
```

El significado de una propiedad calculada es simple: `[fruit]` significa que el nombre de la propiedad debe tomarse de la `fruit`.

Entonces, si un alguien ingresa `"apple"`, la bolsa se convertirá en `{apple: 5}`

```javascript
let fruit = prompt("Which fruit to buy?", "apple");
let bag = {};

// take property name from the fruit variable
bag[fruit] = 5;
```

Básicamente, eso funciona igual que:

```javascript
let fruit = prompt("Which fruit to buy?", "apple");
let bag = {};

// take property name from the fruit variable
bag[fruit] = 5;
```

Podemos usar expresiones más complejas entre corchetes:

```javascript
let fruit = 'apple';
let bag = {
  [fruit + 'Computers']: 5 // bag.appleComputers = 5
};
```

# Property value shorthand
En el código real, a menudo utilizamos variables existentes como valores para los nombres de propiedades.

```javascript
function makeUser(name, age) {
  return {
    name: name,
    age: age,
    // ...other properties
  };
}

let user = makeUser("John", 30);
alert(user.name); // John
```

En el ejemplo anterior, las propiedades tienen los mismos nombres que las variables. El caso de uso de crear una propiedad a partir de una variable es común que existe una abreviatura de valor de propiedad especial para acortarlo.

# Property name limitations
Como ya sabemos, una variable no puede tener un nombre igual a una de las palabras reservadas del idioma como `"for"`, `"let"`, `"return"`, etc.
```javascript
// these properties are all right
let obj = {
  for: 1,
  let: 2,
  return: 3
};

alert( obj.for + obj.let + obj.return );  // 6
```

En resumen, **no existen limitaciones** en cuanto a los **nombres de las propiedades**. Pueden ser cualquier cadena o símbolo (un tipo especial para identificadores, que se tratará más adelante).  
  
Otros tipos **se convierten automáticamente en cadenas.**  
  
Por ejemplo, **un número 0 se convierte en una cadena "0"** cuando se usa como clave de propiedad:

```javascript
let obj = {
  0: "test" // same as "0": "test"
};

// both alerts access the same property (the number 0 is converted to string "0")
alert( obj["0"] ); // test
alert( obj[0] ); // test (same property)
```

Hay un problema menor con una propiedad especial llamada `__proto__`. No podemos establecerlo en un valor que no sea de objeto:

**`__proto__`**:  en JavaScript es una propiedad que indica de qué objeto otro objeto hereda sus propiedades y métodos. Sin embargo, es mejor usar `Object.getPrototypeOf` y `Object.setPrototypeOf` para trabajar con prototipos de manera más segura y estándar.

```javascript
let obj = {};
obj.__proto__ = 5; // assign a number
alert(obj.__proto__); // [object Object] - the value is an object, didn't work as intended
```

`Ejemplo de __proto__`
```js
const obj = {};
const proto = { sayHello: () => console.log('Hello') };

obj.__proto__ = proto;

obj.sayHello(); // Imprime 'Hello'
```


# Property existence test, “in” operator
Una característica notable de los objetos en JavaScript, en comparación con muchos otros lenguajes, es que es posible acceder a cualquier propiedad. ¡No habrá ningún error si la propiedad no existe!

Leer una propiedad inexistente simplemente devuelve `undefined`. Entonces podemos probar fácilmente si la propiedad existe.

```javascript
let user = {};

console.log( user.noSuchProperty === undefined ); // true means "no such property"
```

Entonces al igual que el operador `===` existe  `in` para hacer la comprobación de existencia.

A tener en cuenta es que cuando se usa el operador `in` necesitamos hacer referencia a la propiedad en strings.

```javascript
let user = { name: "John", age: 30 };

alert( "age" in user ); // true, user.age exists
alert( "blabla" in user ); // false, user.blabla doesn't exist
```

Al igual si le pasamos una variable esta debe tener el nombre de la propiedad a referenciar.

```javascript
let user = { age: 30 };

let key = "age";
alert( key in user ); // true, property "age" exists
```

la **syntax** es sencilla.

```js
"key" in obj
```

¿Por qué existe el operador `in`? ¿No es suficiente compararlo con  `undefined`?  
  
Bueno, la mayoría de las veces la comparación con `undefined` funciona bien. Pero hay un caso especial en el que falla, pero "`in`" funciona correctamente.

```javascript
let obj = {
  test: undefined
};

alert( obj.test ); // it's undefined, so - no such property?

alert( "test" in obj ); // true, the property does exist!
```

En el código anterior, la propiedad `obj.test` técnicamente existe. Entonces el operador `in` funciona bien.

Situaciones como esta ocurren muy raramente, porque `undefined` no debe asignarse explícitamente. Principalmente usamos `null` para valores `unknow` o `void`. Entonces el operador `in` es **un invitado exótico** en el código.

# The "for..in" loop
Para recorrer todas las `key` de un objeto, existe una forma especial de bucle: `for..in`. Esto es completamente diferente del constructor `for(;;)` que estudiamos antes.

La sintaxis es:
```javascript
for (key in object) {
  // executes the body for each key among object properties
}
```

Podemos sacar todos los atributos de un objeto:
```javascript
let user = {
  name: "John",
  age: 30,
  isAdmin: true
};

for (let key in user) {
  // keys
  alert( key );  // name, age, isAdmin
  // values for the keys
  alert( user[key] ); // John, 30, true
}
```

Tenga en cuenta que todas las construcciones "for" nos permiten declarar la variable de bucle dentro del bucle, como la tecla let aquí.

Además, aquí podríamos usar otro nombre de variable en lugar de clave.
- Por ejemplo, "`for (let prop in obj)`" también se usa ampliamente.

## Ordered like an object
¿Están ordenados los objetos? En otras palabras, si recorremos un objeto, ¿obtenemos todas las propiedades en el mismo orden en que se agregaron? ¿Podemos confiar en esto?

La respuesta corta es: “ordenadas de una manera especial”: las propiedades de los enteros están ordenadas, otras aparecen en orden de creación. Los detalles siguen.

Como ejemplo, consideremos un objeto con códigos telefónicos:

```javascript
let codes = {
  "49": "Germany",
  "41": "Switzerland",
  "44": "Great Britain",
  // ..,
  "1": "USA"
};

for (let code in codes) {
  console.log(code); // 1, 41, 44, 49
}
```

El objeto puede usarse para sugerir una lista de opciones al usuario. Si estamos creando un sitio principalmente para una audiencia alemana, probablemente queramos que **49** sea el primero.

Pero si ejecutamos el código, vemos una imagen totalmente diferente:  
  
Estados Unidos (1) va primero , luego Suiza (41) y así sucesivamente.

Los códigos telefónicos van en orden ascendente, porque son números enteros. Entonces vemos `1, 41, 44, 49`

### ¿Propiedades Integers? ¿Qué es eso?
El término **"propiedad de número entero"** aquí significa una cadena que se puede convertir hacia y desde un número entero sin realizar cambios.

Entonces, "49" es un nombre de propiedad de número entero, porque cuando se transforma a un número entero y viceversa, sigue siendo el mismo. Pero "+49" y "1.2" no lo son:

```javascript
// Number(...) explicitly converts to a number
// Math.trunc is a built-in function that removes the decimal part
console.log( String(Math.trunc(Number("49"))) ); // "49", same, integer property
console.log( String(Math.trunc(Number("+49"))) ); // "49", not same "+49" ⇒ not integer property
console.log( String(Math.trunc(Number("1.2"))) ); // "1", not same "1.2" ⇒ not integer property
```

Por otro lado, si las claves no son enteras, se enumeran en el orden de creación, por ejemplo:

```javascript
let user = {
  name: "John",
  surname: "Smith"
};
user.age = 25; // add one more

// non-integer properties are listed in the creation order
for (let prop in user) {
  console.log( prop ); // name, surname, age
}
```

Entonces, para solucionar el problema con los códigos telefónicos, podemos "hacer trampa" haciendo que los códigos no sean números enteros. Agregar un signo más "+" antes de cada código es suficiente.

```javascript
let codes = {
  "+49": "Germany",
  "+41": "Switzerland",
  "+44": "Great Britain",
  // ..,
  "+1": "USA"
};

for (let code in codes) {
  alert( +code ); // 49, 41, 44, 1
}
```


# Built-in Objects
Que es un **Built-in object** en JavaScript? , es un objeto que ya viene **predefinido o incorporado** en el lenguaje de programación JavaScript.   

Existen numerosos objetos integrados con el lenguaje JavaScript, **todos** los cuales son accesibles en el **scope global**. Algunos ejemplos son:
- `Number`
- `Math`
- `Date`
- `String`
- `Error`
- `Function`
- `Boolean`

El término **"objetos globales"** (u objetos integrados estándar) aquí **no debe confundirse con el objeto global**. Aquí, "objetos globales" se refiere a objetos en el ámbito global.\

Se puede acceder al objeto global en sí utilizando el operador `this` en el ámbito global. De hecho, **el alcance global consta de las propiedades del objeto global**, incluidas las propiedades heredadas, si las hay.

Otros objetos en el ámbito global son creados por el script del usuario o proporcionados por la aplicación host. Los objetos de host disponibles en los contextos del navegador están documentados en **la referencia de API.**

Todos los tipos de [[Built-in]] Objetos, ademas sus propiedades prototipos en [[Prototypal Inheritance]] y [[Object prototype]]



