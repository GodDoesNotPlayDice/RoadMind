La asincronía en JavaScript se refiere a la capacidad del lenguaje para realizar operaciones que pueden tomar tiempo en completarse (como solicitudes de red, lecturas de archivos, o temporizadores) sin bloquear la ejecución del resto del código. Esto es crucial para mantener la fluidez y la responsividad de las aplicaciones, especialmente en entornos como navegadores web donde las operaciones de larga duración podrían congelar la interfaz de usuario.

## Caracteristicas de la asincronía
- **No bloqueante**: Las operaciones asíncronas permiten que el código continúe ejecutándose mientras se espera que se complete una tarea de larga duración.
- **Callbacks**: Son funciones que se pasan como argumentos a otras funciones y se ejecutan una vez que se completa una operación asíncrona. [[Callbacks]], [[Callback Hell]]
- **Promesas**: Son objetos que representan el resultado eventual de una operación asíncrona. Pueden estar en uno de tres estados: pendiente, cumplida o rechazada. [[Promises]]
- **async/await**: Es una sintaxis más moderna y legible para trabajar con promesas. `async` declara una función asíncrona, y `await` pausa la ejecución hasta que la promesa se resuelva. [[Async Await]]
- **Event Loop**: Es el mecanismo que permite a JavaScript manejar operaciones asíncronas. Aunque JavaScript es monohilo, el Event Loop permite manejar múltiples tareas de manera eficiente. [[Event Loop con Peras y Manzanas]], [[Event Loop]]

```js
// Usando callbacks
function hacerAlgo(callback) {
    setTimeout(function() {
        callback('Hecho');
    }, 1000);
}

hacerAlgo(function(resultado) {
    console.log(resultado); // 'Hecho' después de 1 segundo
});

// Usando promesas
let promesa = new Promise(function(resolver, rechazar) {
    setTimeout(function() {
        resolver('Éxito');
    }, 1000);
});

promesa.then(function(valor) {
    console.log(valor); // 'Éxito' después de 1 segundo
});

// Usando async/await
async function obtenerDatos() {
    let respuesta = await fetch('https://api.api-ninjas.com/v1/dogs?name=golden retriever');
    let datos = await respuesta.json();
    console.log(datos);
}

obtenerDatos();
```

## ¿Porque es importante?
- **Responsividad**: Permite que las aplicaciones sigan siendo interactivas mientras se realizan operaciones de larga duración.
- **Eficiencia**: Aprovecha mejor los recursos del sistema al no bloquear la ejecución del código.
- **Escalabilidad**: Facilita la construcción de aplicaciones que necesitan manejar múltiples tareas simultáneamente, como servidores web.

