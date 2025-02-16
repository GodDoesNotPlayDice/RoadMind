
### Funciones Declarativas
Estas funciones se definen usando la palabra clave `function` seguida del nombre de la función.

```js
function saludar(nombre) {
    return "Hola, " + nombre;
}

console.log(saludar("Juan")); // Output: Hola, Juan
```

### Funciones Anónimas
Estas funciones no tienen nombre y se asignan a una variable o se pasan como argumento a otra función.

```js
const saludar = function(nombre) {
    return "Hola, " + nombre;
};

console.log(saludar("Ana")); // Output: Hola, Ana
```

### Funciones Flecha
Las funciones flecha son una sintaxis más corta para escribir funciones anónimas. Se definen usando `=>`.

```js
const saludar = (nombre) => {
    return "Hola, " + nombre;
};

console.log(saludar("Carlos")); // Output: Hola, Carlos
```

Si la función tiene una sola línea de código y devuelve un valor, puedes omitir las llaves `{}` y la palabra clave `return`:

```js
const saludar = (nombre) => "Hola, " + nombre;

console.log(saludar("Laura")); // Output: Hola, Laura
```

### Funciones Autoinvocadas
Estas funciones se ejecutan inmediatamente después de ser definidas. Se colocan entre paréntesis y se les añade otro par de paréntesis al final para invocarlas.

```js
(function() {
    console.log("Esta función se ejecuta inmediatamente");
})();
```

### Funciones Constructoras
Estas funciones se utilizan para crear objetos. Se definen con la palabra clave `function` y se invocan con la palabra clave `new`.

```js
function Persona(nombre, edad) {
    this.nombre = nombre;
    this.edad = edad;
}

const persona1 = new Persona("Pedro", 30);
console.log(persona1.nombre); // Output: Pedro
```

### Funciones como Métodos
Las funciones pueden ser propiedades de objetos y se llaman métodos cuando están dentro de un objeto.

```js
const persona = {
    nombre: "Maria",
    saludar: function() {
        return "Hola, " + this.nombre;
    }
};

console.log(persona.saludar()); // Output: Hola, Maria
```

### Funciones con parámetros por defecto
Puedes definir valores por defecto para los parámetros de una función.

```js
function saludar(nombre = "Invitado") {
    return "Hola, " + nombre;
}

console.log(saludar()); // Output: Hola, Invitado
console.log(saludar("Sofia")); // Output: Hola, Sofia
```

### Funciones que devuelven otras funciones (Clousers)
Las funciones pueden devolver otras funciones, lo que permite crear closures. [[Closures]]

```js
function crearSaludo(saludo) {
    return function(nombre) {
        return saludo + ", " + nombre;
    };
}

const saludarEnEspanol = crearSaludo("Hola");
console.log(saludarEnEspanol("Luis")); // Output: Hola, Luis
```

### Funciones Recursivas
Una función recursiva es aquella que se llama a sí misma. [[Funciones recursivas]]

```js
function factorial(n) {
    if (n === 0) {
        return 1;
    }
    return n * factorial(n - 1);
}

console.log(factorial(5)); // Output: 120
```

### Funciones Generadoras (Generators)
Las funciones generadoras permiten pausar y reanudar la ejecución de una función. Se definen con `function*` y usan `yield` para pausar la ejecución.

```js
function* generador() {
    yield 1;
    yield 2;
    yield 3;
}

const gen = generador();
console.log(gen.next().value); // Output: 1
console.log(gen.next().value); // Output: 2
console.log(gen.next().value); // Output: 3
```

### Funciones (Async / Await)
Las funciones asíncronas permiten trabajar con código asíncrono de manera más sencilla. Se definen con `async` y usan `await` para esperar a que una promesa se resuelva.

```js
async function obtenerDatos() {
    const respuesta = await fetch('https://api.sampleapis.com/beers/ale');
    const datos = await respuesta.json();
    return datos;
}

obtenerDatos().then(datos => console.log(datos));
```


### Funciones Callback
Las funciones callback son funciones que se pasan como argumentos a otras funciones y se ejecutan después de que se complete alguna operación.

```js
function procesarEntrada(entrada, callback) {
    console.log("Procesando entrada...");
    callback(entrada);
}

procesarEntrada("Datos", function(datos) {
    console.log("Datos procesados: " + datos);
});
```


### Funciones de Orden superior (Higher-Order Functions)
Estas son funciones que toman otras funciones como argumentos o devuelven funciones.

```js
function multiplicarPor(factor) {
    return function(numero) {
        return numero * factor;
    };
}

const duplicar = multiplicarPor(2);
console.log(duplicar(5)); // Output: 10
```

### Funciones con Rest parameters
Los rest parameters permiten pasar un número variable de argumentos a una función como un array.

```js
function sumar(...numeros) {
    return numeros.reduce((total, num) => total + num, 0);
}

console.log(sumar(1, 2, 3, 4)); // Output: 10
```


### Funciones con destructuring en parámetros
Puedes usar destructuring para extraer valores de objetos o arrays pasados como parámetros.

```js
function mostrarNombre({ nombre, apellido }) {
    console.log(nombre + " " + apellido);
}

const persona = { nombre: "Juan", apellido: "Perez" };
mostrarNombre(persona); // Output: Juan Perez
```

### Funciones con parámetros opcionales
Puedes hacer que algunos parámetros sean opcionales usando destructuring con valores por defecto.

```js
function mostrarInfo({ nombre = "Invitado", edad = 18 }) {
    console.log(`Nombre: ${nombre}, Edad: ${edad}`);
}

mostrarInfo({ nombre: "Carlos" }); // Output: Nombre: Carlos, Edad: 18
```

### Funciones con `this` y `bind`
El valor de `this` en una función depende de cómo se llama la función. Puedes usar `bind` para establecer el valor de `this`.

```js
const persona = {
    nombre: "Ana",
    saludar: function() {
        console.log("Hola, " + this.nombre);
    }
};

const saludar = persona.saludar.bind(persona);
saludar(); // Output: Hola, Ana
```

### Funciones con `new.target`
`new.target` permite detectar si una función fue llamada con `new`.

```js
function Persona(nombre) {
    if (!new.target) {
        return new Persona(nombre);
    }
    this.nombre = nombre;
}

const persona = Persona("Juan");
console.log(persona.nombre); // Output: Juan
```

### Funciones con `Symbol.iterator`
Puedes definir un iterador personalizado para un objeto usando `Symbol.iterator`.

```js
const miObjeto = {
    *[Symbol.iterator]() {
        yield 1;
        yield 2;
        yield 3;
    }
};

for (let valor of miObjeto) {
    console.log(valor); // Output: 1, 2, 3
}
```


### Funciones con `proxy`
`Proxy` permite definir comportamiento personalizado para operaciones fundamentales en un objeto.

```js
const objetivo = {
    mensaje: "Hola"
};

const proxy = new Proxy(objetivo, {
    get: function(objetivo, propiedad) {
        return propiedad in objetivo ? objetivo[propiedad] : "Propiedad no encontrada";
    }
});

console.log(proxy.mensaje); // Output: Hola
console.log(proxy.otraPropiedad); // Output: Propiedad no encontrada
```

### Funciones con `Reflect`
`Reflect` es un objeto que proporciona métodos para realizar operaciones sobre objetos.

```js
const objeto = {
    nombre: "Pedro"
};

console.log(Reflect.get(objeto, "nombre")); // Output: Pedro
Reflect.set(objeto, "nombre", "Juan");
console.log(objeto.nombre); // Output: Juan
```


### Funciones con `promise`
Las promesas permiten manejar operaciones asíncronas de manera más limpia.

```js
const promesa = new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve("Datos recibidos");
    }, 1000);
});

promesa.then(datos => console.log(datos)); // Output: Datos recibidos
```

### Funciones con `map`, `filter` y `reduce`

```js
const numeros = [1, 2, 3, 4, 5];

const duplicados = numeros.map(num => num * 2);
console.log(duplicados); // Output: [2, 4, 6, 8, 10]

const pares = numeros.filter(num => num % 2 === 0);
console.log(pares); // Output: [2, 4]

const suma = numeros.reduce((total, num) => total + num, 0);
console.log(suma); // Output: 15
```


### Funciones con Null

#### Optional Chaining
El encadenamiento opcional permite acceder a propiedades de objetos anidados sin tener que verificar si cada nivel existe.

```js
const usuario = {
    perfil: {
        nombre: "Juan"
    }
};

console.log(usuario.perfil?.nombre); // Output: Juan
console.log(usuario.direccion?.calle); // Output: undefined
```

#### Nullish coalescing
El operador de coalescencia nula (`??`) permite devolver un valor predeterminado solo si el valor es `null` o `undefined`.

```js
const valor = null;
console.log(valor ?? "Valor predeterminado"); // Output: Valor predeterminado
```

#### Logical assignment operators
Los operadores de asignación lógica permiten asignar un valor solo si la variable es `null`, `undefined`, `false`, etc.

```js
let a = null;
a ||= "valor predeterminado";
console.log(a); // Output: valor predeterminado
```

