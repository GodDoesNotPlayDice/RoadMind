TypeScript, como un superconjunto de JavaScript, incluye varios tipos primitivos que son fundamentales para definir el tipo de datos que pueden almacenar las variables

[[Tipos de datos]] en JavaScript.

## Boolean
Representa un valor verdadero o falso. Es el tipo más básico y se utiliza para declarar variables que solo pueden contener `true` o `false`.

```ts
let isDone: boolean = false;
```
## Number
En TypeScript, todos los valores numéricos son de tipo `number`, ya sean enteros o decimales. TypeScript soporta números binarios, octales, decimales y hexadecimales.

```ts
let decimal: number = 6;
let hex: number = 0xf00d;
let binary: number = 0b1010;
let octal: number = 0o744;
```
## String
Representa una secuencia de caracteres y se utiliza para texto. Puedes usar comillas simples (`'`), dobles (`"`) o backticks (`` ` ``) para definir cadenas de texto.

```ts
let color: string = "blue";
color = 'red';
let fullName: string = `Bob Bobbington`;
let age: number = 37;
let sentence: string = `Hello, my name is ${fullName}. I'll be ${age + 1} years old next month.`;
```
## Void
Se utiliza principalmente para indicar que una función no devuelve ningún valor. No es un tipo que puedas asignar a una variable.

```ts
function warnUser(): void {
    console.log("This is a warning message");
}
```
## undefined, null
Estos tipos se utilizan para representar los valores `undefined` y `null` en JavaScript. En TypeScript, ambos tienen sus propios tipos llamados `undefined` y `null`, respectivamente. Por defecto, estos tipos son subtipos de todos los otros tipos, lo que significa que puedes asignar `null` y `undefined` a una variable de tipo `number`

```ts
let u: undefined = undefined;
let n: null = null;
```

