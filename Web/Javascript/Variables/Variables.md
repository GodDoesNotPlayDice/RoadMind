
**const**: Las constantes **tienen un alcance de bloque**, al igual que **las variables declaradas usando la palabra clave `let`**. El valor de una **constante no se puede cambiar mediante reasignación** (es decir, mediante el uso del operador de asignación) y **no se puede volver a declarar** (es decir, mediante una declaración de variable). Sin embargo, si una constante es **un objeto o una matriz, sus propiedades o elementos se pueden actualizar o eliminar.**

**var**: La declaración var declara una variable con ámbito de función o de ámbito global, y opcionalmente la inicializa en un valor. (no usar.)

**let**: La declaración `let` declara una **variable local con ámbito de bloque** y, opcionalmente, la inicializa con un valor.

Para usar variables en JavaScript, primero debemos crearlas, es decir, declarar una variable. Para declarar variables, utilizamos una de las palabras clave `var`, `let` o `const`.
```js
const hello = "Hello world"
const f_hey = () => {
  console.log(hello)
}
let hi = "Hello world"
var hola = "Hello world"

console.log(hello)
console.log(hi)
console.log(hola)
```

# Hoisting
**Hoisting en JavaScript** es como si el intérprete de **JavaScript** tomara todas las declaraciones de variables y funciones y las "**levantara**" hacia la parte superior de su alcance (scope) antes de que el código se ejecute.

```js
console.log(nombre); // undefined
var nombre = "Santiago";
```

Aunque la variable `nombre` se declara después del `console.log`, debido al hoisting, JavaScript trata la declaración como si fuera así:


```js
var nombre;
console.log(nombre); // undefined
nombre = "Santiago";
```

# Naming
La mejor buena practica es nombrar las variables por lo que son y por uso común cosa de que sea mas fácil de entender y de mantener para otras personas, para saber mas de [Naming](https://www.codeguage.com/courses/js/variables#Tips_for_naming_variables)


# Scope
En JavaScript, el alcance **se refiere a la visibilidad de una variable** o **cómo se puede usar después de declararla.** El alcance de una variable depende de la palabra clave que se utilizó para declararla.

Los **tres tipos de alcance** son **alcance global, alcance de función y alcance de bloque**. Antes de ES6 (2015), JavaScript solo tenía alcance global y alcance de función con la palabra clave var. ES6 introdujo let y const que permiten Block Scope en JavaScript.

```js
let saludo;
console.log(saludo); // undefined
saludo = "Holaa";
```


**Scope global:** las variables **declaradas fuera de cualquier función o llaves '{}'** tienen alcance global y se puede acceder a ellas desde cualquier lugar dentro del mismo código **JavaScript**.  `var let const`  proporcionan este alcance.

**Alcance del bloque:** un bloque es cualquier parte del **código JavaScript delimitada por '{}'.** No se puede acceder a las variables declaradas dentro de un bloque fuera de ese bloque. Este alcance solo lo proporcionan las palabras clave let y const. Si declara una variable dentro de un bloque usando la palabra clave var, NO tendrá alcance de bloque.

**Alcance de la función:** las variables declaradas dentro de una función **solo se pueden usar dentro de esa misma función.** Fuera de esa función, no están definidos. `var let const` proporcionan este alcance.

**Alcance local:** las variables locales solo **se reconocen dentro de sus funciones, las variables con el mismo nombre se pueden usar en diferentes funciones.** Las variables locales se crean cuando se inicia una función y se eliminan cuando se completa la función. `var let const`  proporcionan este alcance.

## Block
Este alcance restringe el acceso de la variable que se declara dentro de un bloque específico desde el exterior del bloque. La **palabra clave let & const facilita el alcance del bloque** de las variables. Para acceder a las variables de ese bloque específico, necesitamos crear un objeto para él. Las variables declaradas **con la palabra clave var no tienen alcance de bloque.**


## Function
Cuando se **declara una variable dentro de una función, solo se puede acceder a ella dentro de esa función** y no se puede usar fuera de esa función.

## Global
Las variables **declaradas globalmente (fuera de cualquier función) tienen alcance global.** Se puede acceder a las **variables globales desde cualquier lugar en un programa JavaScript.** Las variables declaradas **con var, let y const son bastante similares cuando se declaran fuera de un bloque.**

