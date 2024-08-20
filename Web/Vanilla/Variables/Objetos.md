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

