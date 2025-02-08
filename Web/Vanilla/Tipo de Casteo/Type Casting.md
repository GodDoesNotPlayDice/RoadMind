La mayoría de las veces, los operadores y funciones convierten automáticamente los valores que se les dan al tipo correcto.  
  
Por ejemplo, la alerta convierte automáticamente cualquier valor en una cadena para mostrarlo. Las operaciones matemáticas convierten valores en números.  
  
También hay casos en los que necesitamos convertir explícitamente un valor al tipo esperado.

# String
Podemos convertir cualquier valor posible a un `string`

```js
const number = 12

const value_to_string = String(number)

console.log(value_to_string)
```

```javascript
let value = true;
alert(typeof value); // boolean

value = String(value); // now value is a string "true"
alert(typeof value); // string
```

La conversión de cadenas es bastante obvia. Un falso se convierte en "false", un nulo se convierte en "null", etc.


# Numeric
La conversión numérica en funciones y expresiones matemáticas se produce automáticamente.  
  
Por ejemplo, cuando la división `/` se aplica a elementos que no son números:
```javascript
console.log( "6" / "2" ); // 3, strings are converted to numbers
```

Podemos usar la función `Number(value)` para convertir explícitamente un valor en un número:

```javascript
let str = "123";
alert(typeof str); // string

let num = Number(str); // becomes a number 123

alert(typeof num); // number
```


Por lo general, se requiere una conversión explícita cuando leemos un valor de una fuente basada en cadenas, como un formulario de texto, pero esperamos que se ingrese un número.  
  
Si la cadena no es un número válido, el resultado de dicha conversión es **NaN**. 

Por **ejemplo**:
```javascript
let age = Number("an arbitrary string instead of a number");

alert(age); // NaN, conversion failed
```

| Value              | Becomes...                                                                                                                                                                                                                                                              |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `undefined`        | `NaN`                                                                                                                                                                                                                                                                   |
| `null`             | `0`                                                                                                                                                                                                                                                                     |
| `true` and `false` | `1` and `0`                                                                                                                                                                                                                                                             |
| `string`           | Los espacios en blanco (incluye espacios, tabulaciones `\t`, saltos de línea `\n`, etc.) al inicio y al final se eliminan. Si la cadena resultante está vacía, el resultado es `0`. De lo contrario, el número se "lee" de la cadena. Un error da como resultado `NaN`. |
```javascript
alert( Number("   123   ") ); // 123
alert( Number("123z") );      // NaN (error reading a number at "z")
alert( Number(true) );        // 1
alert( Number(false) );       // 0
```

Tenga en cuenta que nulo y undefinido se comportan de manera diferente aquí: nulo se convierte en cero mientras que undefinido se convierte en NaN.  
  
La mayoría de los operadores matemáticos también realizan este tipo de conversión, lo veremos en el próximo capítulo.

# Boolean
La conversión booleana es la más sencilla.  
  
Sucede en operaciones lógicas (más adelante veremos pruebas de condición y otras cosas similares) pero también se puede realizar explícitamente con una llamada a Boolean(value).  
  
La regla de conversión:
- Los valores que intuitivamente están "vacíos", como 0, una cadena vacía, nulo, indefinido y **NaN**, se vuelven falsos.  
- Otros valores se vuelven realidad.

```javascript
alert( Boolean(1) ); // true
alert( Boolean(0) ); // false

alert( Boolean("hello") ); // true
alert( Boolean("") ); // false
```


| Original Value       | Converted to Number | Converted to String      | Converted to Boolean |
|----------------------|---------------------|---------------------------|-----------------------|
| `false`              | 0                   | `"false"`                 | `false`              |
| `true`               | 1                   | `"true"`                  | `true`               |
| 0                    | 0                   | `"0"`                     | `false`              |
| 1                    | 1                   | `"1"`                     | `true`               |
| `"0"`                | 0                   | `"0"`                     | `true`               |
| `"000"`              | 0                   | `"000"`                   | `true`               |
| `"1"`                | 1                   | `"1"`                     | `true`               |
| `NaN`                | `NaN`               | `"NaN"`                   | `false`              |
| `Infinity`           | `Infinity`          | `"Infinity"`              | `true`               |
| `-Infinity`          | `-Infinity`         | `"-Infinity"`             | `true`               |
| `""`                 | 0                   | `""`                      | `false`              |
| `"20"`               | 20                  | `"20"`                    | `true`               |
| `"twenty"`           | `NaN`               | `"twenty"`                | `true`               |
| `[]`                 | 0                   | `""`                      | `true`               |
| `[20]`               | 20                  | `"20"`                    | `true`               |
| `[10,20]`            | `NaN`               | `"10,20"`                 | `true`               |
| `["twenty"]`         | `NaN`               | `"twenty"`                | `true`               |
| `["ten","twenty"]`   | `NaN`               | `"ten,twenty"`            | `true`               |
| `function(){}`       | `NaN`               | `"function(){}"`          | `true`               |
| `{}`                 | `NaN`               | `"[object Object]"`       | `true`               |
| `null`               | 0                   | `"null"`                  | `false`              |
| `undefined`          | `NaN`               | `"undefined"`             | `false`              |

```js
const a = "3"
const b = "5"
console.log(a * b)
```

Luego sigue lo que seria el [[Data Structure]]