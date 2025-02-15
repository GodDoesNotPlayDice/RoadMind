## Value properties
Estas propiedades globales devuelven un valor simple. No tienen propiedades ni métodos, osea un adorno

- `globalThis`: Devuelve el valor del objeto global, este sirve o servia para acceder al objeto global en cualquier contexto.
- `Infinity`: Un valor numérico que representa infinito, sirve para representar un valor numérico infinito.
- `NaN`: Un valor numérico que representa no un número, sirve para representar un valor no numérico.
- `undefined`: Un valor primitivo que representa la ausencia intencional de cualquier valor o propiedad. 

## Function properties
Estas propiedades globales devuelven una función o un objeto que es una función.

- `eval()`: Evalúa JavaScript code representado como una cadena, sirve cuando se necesita evaluar una cadena de código JavaScript.
- `isFinite()`: Determina si el valor pasado es un número finito, sirve para determinar si un valor es finito.
-  `isNaN()`: Determina si un valor es NaN o no, sirve para determinar si un valor es NaN.
- `parseFloat()`: Parsea un argumento de cadena y devuelve un número de punto flotante, sirve para convertir una cadena en un número de punto flotante.
- `parseInt()`: Parsea un argumento de cadena y devuelve un entero de la base especificada, sirve para convertir una cadena en un entero.
- `decodeURI()`: Decodifica un URI completo, sirve para decodificar un URI completo.
- `decodeURIComponent()`: Decodifica un componente URI, sirve para decodificar un componente de URI.
- `encodeURI()`: Codifica un URI completo, sirve para codificar un URI completo.
- `encodeURIComponent()`: Codifica un componente URI, sirve para codificar un componente de URI.
- `escape()`: Obsoleto, usa encodeURI o encodeURIComponent en su lugar, sirve para escapar una cadena.
- `unescape()`: Obsoleto, usa decodeURI o decodeURIComponent en su lugar, sirve para deshacer el escape de una cadena.

## Fundamental objects
Estos objetos representan construcciones fundamentales del lenguaje.

- `Object`: Crea un nuevo objeto, sirve para crear un nuevo objeto. [[Objetos]]
- `Function`: Crea una nueva función, sirve para crear una nueva función.  
- `Boolean`: Crea un nuevo objeto de tipo Boolean, sirve para crear un nuevo objeto de tipo Boolean.
- `Symbol`: Crea un nuevo objeto de tipo Symbol, sirve para crear un nuevo objeto de tipo Symbol. 

## Error Objects
Estos objetos representan un error cuando una operación falla.

- `Error`: Crea una instancia de un nuevo error, sirve para crear una instancia de un nuevo error.
- `AggregateError`: Crea una nueva instancia de un objeto AggregateError, sirve para crear una nueva instancia de un objeto AggregateError.
- `EvalError`: Crea una instancia de un nuevo error EvalError, sirve para crear una instancia de un nuevo error EvalError.
- `InternalError`: Crea una instancia de un nuevo error InternalError, sirve para crear una instancia de un nuevo error InternalError. (**deprecated**)
- `RangeError`: Crea una instancia de un nuevo error RangeError, sirve para crear una instancia de un nuevo error RangeError.
- `ReferenceError`: Crea una instancia de un nuevo error ReferenceError, sirve para crear una instancia de un nuevo error ReferenceError.
- `SyntaxError`: Crea una instancia de un nuevo error SyntaxError, sirve para crear una instancia de un nuevo error SyntaxError.
- `TypeError`: Crea una instancia de un nuevo error TypeError, sirve para crear una instancia de un nuevo error TypeError.
- `URIError`: Crea una instancia de un nuevo error URIError, sirve para crear una instancia de un nuevo error URIError.


## Numbers and dates
Estos objetos te permiten trabajar con valores numéricos y fechas.

- `Number`: Crea un nuevo objeto de tipo Number, sirve para crear un nuevo objeto de tipo Number.
- `BigInt`: Crea un nuevo objeto de tipo BigInt, sirve para crear un nuevo objeto de tipo BigInt.
- `Math`: Proporciona propiedades y métodos para funciones matemáticas estáticas, sirve para proporcionar propiedades y métodos para funciones matemáticas estáticas.
- `Date`: Crea un nuevo objeto de tipo Date, sirve para crear un nuevo objeto de tipo Date.

## Text processing
Estos objetos te permiten trabajar con cadenas de texto.

- `String`: Crea un nuevo objeto de tipo String, sirve para crear un nuevo objeto de tipo String.
- `RegExp`: Crea un nuevo objeto de tipo RegExp, sirve para crear un nuevo objeto de tipo RegExp.

## Indexed collections
Estos objetos te permiten trabajar con colecciones de datos ordenados.

- `Array`: Crea un nuevo objeto de tipo Array, sirve para crear un nuevo objeto de tipo Array.
- `Int8Array`: Crea un nuevo objeto de tipo Int8Array, sirve para crear un nuevo objeto de tipo Int8Array y usarlo cuando  necesitas trabajar con datos binarios.
- `Uint8Array`: Crea un nuevo objeto de tipo Uint8Array, sirve para crear un nuevo objeto de tipo Uint8Array.
- `Uint8ClampedArray`: Crea un nuevo objeto de tipo Uint8ClampedArray, sirve para crear un nuevo objeto de tipo Uint8ClampedArray.
- `Int16Array`: Crea un nuevo objeto de tipo Int16Array, sirve para crear un nuevo objeto de tipo Int16Array.
- `Uint16Array`: Crea un nuevo objeto de tipo Uint16Array, sirve para crear un nuevo objeto de tipo Uint16Array.
- `Int32Array`: Crea un nuevo objeto de tipo Int32Array, sirve para crear un nuevo objeto de tipo Int32Array.
- `Uint32Array`: Crea un nuevo objeto de tipo Uint32Array, sirve para crear un nuevo objeto de tipo Uint32Array.
- `Float32Array`: Crea un nuevo objeto de tipo Float32Array, sirve para crear un nuevo objeto de tipo Float32Array.
- `Float64Array`: Crea un nuevo objeto de tipo Float64Array, sirve para crear un nuevo objeto de tipo Float64Array.
- `BigInt64Array`: Crea un nuevo objeto de tipo BigInt64Array, sirve para crear un nuevo objeto de tipo BigInt64Array.
- `BigUint64Array`: Crea un nuevo objeto de tipo BigUint64Array, sirve para crear un nuevo objeto de tipo BigUint64Array.

## Keyed collections
Estos objetos te permiten trabajar con colecciones de datos que se pueden acceder por una clave.

- `Map`: Crea un nuevo objeto de tipo Map, sirve para crear un nuevo objeto de tipo Map esto es muy util cuando necesitas almacenar pares clave-valor.
- `Set`: Crea un nuevo objeto de tipo Set, sirve para crear un nuevo objeto de tipo Set, esto es muy util cuando necesitas almacenar valores únicos.
- `WeakMap`: Crea un nuevo objeto de tipo WeakMap, sirve para crear un nuevo objeto de tipo WeakMap, es muy util cuando necesitas almacenar pares clave-valor débiles.
- `WeakSet`: Crea un nuevo objeto de tipo WeakSet, sirve para crear un nuevo objeto de tipo WeakSet, es muy util cuando necesitas almacenar valores únicos débiles.

## Structured data
Estos objetos te permiten trabajar con datos estructurados, un dato estructurado es un dato que puede ser representado en una estructura de datos.

- `ArrayBuffer`: Crea un nuevo objeto de tipo ArrayBuffer, sirve para crear un nuevo objeto de tipo ArrayBuffer.
- `SharedArrayBuffer`: Crea un nuevo objeto de tipo SharedArrayBuffer, sirve para crear un nuevo objeto de tipo SharedArrayBuffer.
- `Atomics`: Proporciona operaciones atómicas como `add`, `sub`, `and`, `or`, `xor`, `load`, `store`, `exchange`, `compareExchange`, sirve para proporcionar operaciones atómicas.
- `DataView`: Crea un nuevo objeto de tipo DataView, sirve para crear un nuevo objeto de tipo DataView.
- `JSON`: Proporciona métodos para trabajar con JSON, sirve para proporcionar métodos para trabajar con JSON.

## Managing memory
Estos objetos te permiten trabajar con la memoria, la memoria es un recurso muy importante en la programación y en js hay que tener cuidado con ella.

Estos objetos interactúan con el mecanismo de `garGarbage Collection` de JavaScript.

- `WeeakRef`: Crea un nuevo objeto de tipo WeakRef, sirve para crear un nuevo objeto de tipo WeakRef y ademas es muy util cuando necesitas almacenar referencias débiles pero se diferencia de WeakMap y WeakSet en que WeakRef almacena una referencia débil a un objeto.
- `FinalizationRegistry`: Crea un nuevo objeto de tipo FinalizationRegistry, sirve para crear un nuevo objeto de tipo FinalizationRegistry y ademas es muy util cuando necesitas realizar tareas de limpieza cuando un objeto se recolecta.

## Control abstraction objects
Las abstracciones de control pueden ayudar a estructurar el código, especialmente el código asíncrono (sin utilizar devoluciones de `callbacks` profundamente anidadas, por ejemplo).

- `Promise`: Crea un nuevo objeto de tipo Promise, sirve para crear un nuevo objeto de tipo Promise y este es utilizado cuando necesitas realizar tareas asíncronas.
- `Generator`: Crea un nuevo objeto de tipo Generator, sirve para crear un nuevo objeto de tipo Generator y es muy util cuando necesitas realizar tareas iterativas.
- `GeneratorFunction`: Crea un nuevo objeto de tipo GeneratorFunction, sirve para crear un nuevo objeto de tipo GeneratorFunction y es muy util cuando necesitas crear funciones generadoras.
- `AsyncFunction`: Crea un nuevo objeto de tipo AsyncFunction, sirve para crear un nuevo objeto de tipo AsyncFunction y es muy util cuando necesitas crear funciones asíncronas.
- `AsyncGenerator`: Crea un nuevo objeto de tipo AsyncGenerator, sirve para crear un nuevo objeto de tipo AsyncGenerator y es muy util cuando necesitas realizar tareas iterativas asíncronas.

## Reflection
Estos objetos te permiten inspeccionar y manipular el código en tiempo de ejecución.

- `Reflect`: Proporciona métodos para la reflexión, sirve para proporcionar métodos para la reflexión, la reflexión es la capacidad de un programa para examinar y modificar su estructura y comportamiento en tiempo de ejecución.
- `Proxy`: Crea un nuevo objeto de tipo Proxy, sirve para crear un nuevo objeto de tipo Proxy y es muy util cuando necesitas realizar tareas de metaprogramación.

## Internationalization
Estos objetos te permiten trabajar con datos internacionales, es decir, datos que están en diferentes idiomas.

- `Intl`: Proporciona objetos para internacionalización, sirve para proporcionar objetos para internacionalización, ademas se puede ocupar cuando necesitas trabajar con fechas, números y cadenas de texto en diferentes idiomas.
- `Intl.Collator`: Crea un nuevo objeto de tipo Intl.Collator, sirve para crear un nuevo objeto de tipo Intl.Collator y es muy util cuando necesitas comparar cadenas de texto en diferentes idiomas.
- `Intl.DateTimeFormat`: Crea un nuevo objeto de tipo Intl.DateTimeFormat, sirve para crear un nuevo objeto de tipo Intl.DateTimeFormat y es muy util cuando necesitas trabajar con fechas en diferentes idiomas.
- `Intl.ListFormat`: Crea un nuevo objeto de tipo Intl.ListFormat, sirve para crear un nuevo objeto de tipo Intl.ListFormat y es muy util cuando necesitas formatear listas en diferentes idiomas.
- `Intl.NumberFormat`: Crea un nuevo objeto de tipo Intl.NumberFormat, sirve para crear un nuevo objeto de tipo Intl.NumberFormat y es muy util cuando necesitas trabajar con números en diferentes idiomas.
- `Intl.PluralRules`: Crea un nuevo objeto de tipo Intl.PluralRules, sirve para crear un nuevo objeto de tipo Intl.PluralRules y es muy util cuando necesitas trabajar con reglas de pluralización en diferentes idiomas.
- `Intl.RelativeTimeFormat`: Crea un nuevo objeto de tipo Intl.RelativeTimeFormat, sirve para crear un nuevo objeto de tipo Intl.RelativeTimeFormat y es muy util cuando necesitas trabajar con fechas relativas en diferentes idiomas.


