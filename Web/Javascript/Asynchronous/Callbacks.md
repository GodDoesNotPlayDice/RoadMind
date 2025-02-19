Los **callbacks** en JavaScript son funciones que se pasan como argumentos a otras funciones y que se ejecutan después de que ocurra algún evento o se complete alguna operación. Son fundamentales en JavaScript, especialmente en operaciones asíncronas como solicitudes de red, temporizadores, o lectura de archivos.

**Ejemplo básico de callback**
```js
function saludar(nombre, callback) {
    console.log("Hola, " + nombre);
    callback(); // Llamamos al callback
}

function despedir() {
    console.log("Adiós!");
}

saludar("Juan", despedir);
```

1. La función `saludar` recibe un nombre y un callback.
2. Después de imprimir el saludo, ejecuta el callback (`despedir`).

## Callbacks en operaciones asíncronas
Los callbacks son muy comunes en operaciones asíncronas. Por ejemplo, con `setTimeout`:

```js
setTimeout(function() {
    console.log("Este mensaje se muestra después de 2 segundos.");
}, 2000);
```

## Callbacks en funciones de array
JavaScript también utiliza callbacks en métodos de arrays como `map`, `filter`, y `forEach`:

```js
const numeros = [1, 2, 3, 4, 5];

const duplicados = numeros.map(function(numero) {
    return numero * 2;
});

console.log(duplicados); // [2, 4, 6, 8, 10]
```

## Los callbacks en la asíncrona
JavaScript utiliza un modelo **asíncrono**. En lugar de esperar a que la tarea termine, el programa sigue ejecutando otras cosas y, cuando la tarea asíncrona termina, se ejecuta un **callback**.
### Ejemplo con `setTimeout`
1) El método `setTimeout` es un ejemplo clásico de asincronía en JavaScript.
2) Recibe un callback y un tiempo en milisegundos. 
3) Después de ese tiempo, el callback se ejecuta.
```js
console.log("Inicio");

setTimeout(function() {
    console.log("Esto se ejecuta después de 2 segundos");
}, 2000);

console.log("Fin");

// Output:
// Inicio
// Fin
// Esto se ejecuta después de 2 segundos
```

1. JavaScript ejecuta el primer `console.log("Inicio")`.
2. Luego, encuentra el `setTimeout` y lo registra para ejecutarse después de 2 segundos, pero **no espera** a que termine.
3. Inmediatamente ejecuta el `console.log("Fin")`.
4. Después de 2 segundos, el callback dentro de `setTimeout` se ejecuta.
### Callbacks en operaciones de I/O (Entrada / Salida)
Un caso común de asincronía es la lectura de archivos o la realización de solicitudes HTTP. Aquí te muestro un ejemplo con `setTimeout` simulando una operación de lectura de archivos:

```js
function leerArchivo(callback) {
    setTimeout(function() {
        const contenido = "Este es el contenido del archivo.";
        callback(contenido);
    }, 1000);
}

console.log("Leyendo archivo...");

leerArchivo(function(contenido) {
    console.log("Archivo leído:", contenido);
});

console.log("Haciendo otras cosas...");
```

1. Se llama a `leerArchivo` y se pasa un callback.
2. La función `leerArchivo` simula una operación de lectura que toma 1 segundo.
3. Mientras se "lee" el archivo, el programa sigue ejecutando otras cosas (`console.log("Haciendo otras cosas...")`).
4. Después de 1 segundo, el callback se ejecuta con el contenido del archivo.


### Callbacks en solicitudes HTTP (simuladas)
Aquí te muestro un ejemplo de cómo se podrían usar callbacks para manejar una solicitud HTTP simulada:

```js
function hacerSolicitudHTTP(url, callback) {
    setTimeout(function() {
        const respuesta = `Datos recibidos de ${url}`;
        callback(respuesta);
    }, 1500);
}

console.log("Iniciando solicitud HTTP...");

hacerSolicitudHTTP("https://api.ejemplo.com/datos", function(respuesta) {
    console.log("Respuesta recibida:", respuesta);
});

console.log("Esperando la respuesta...");
```
