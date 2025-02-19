El **Event Loop** es un mecanismo en JavaScript que permite manejar operaciones **asíncronas** sin bloquear la ejecución del código. Aquí está cómo funciona paso a paso:

## Caracteristicas

### Call Stack (Pila de llamadas)
- Es donde JavaScript lleva un registro de las funciones que se están ejecutando.
- Cuando llamas a una función, esta se añade a la pila. Cuando la función termina, se saca de la pila.
- JavaScript es **monohilo**, lo que significa que solo puede ejecutar una cosa a la vez en el call stack.

### Operaciones Asíncronas
- Algunas operaciones, como `setTimeout`, `fetch`, o `Promise`, `setInterval`, toman tiempo en completarse.
- Estas operaciones no se ejecutan directamente en el call stack. En su lugar, se delegan a otros componentes del entorno de ejecución (como el navegador o Node.js).

### Callback Queue (Cola de Callbacks)
- Cuando una operación asíncrona termina, su **callback** (la función que debe ejecutarse cuando la operación termina) se coloca en la **cola de callbacks**.
- Por ejemplo, si usas `setTimeout`, el callback se añade a la cola después de que el temporizador expire.

### Event Loop
- El Event Loop es un proceso que **revisa constantemente** si el call stack está vacío.
- Cuando el call stack está vacío, el Event Loop toma el primer callback de la cola y lo mueve al call stack para que se ejecute.
- Esto asegura que las operaciones asíncronas se ejecuten en el orden correcto, sin bloquear el hilo principal.

## Ejemplo técnico

```js
console.log("Inicio"); // 1. Esto se ejecuta de inmediato

// setTimeout: Ejecuta una función después de un tiempo específico
setTimeout(() => {
    console.log("setTimeout: Esto se ejecuta después de 2 segundos"); // 4. Esto se ejecuta después de 2 segundos
}, 2000);

// fetch: Realiza una solicitud HTTP (usaremos una API falsa para el ejemplo)
fetch('https://jsonplaceholder.typicode.com/todos/1')
    .then(response => response.json())
    .then(data => {
        console.log("fetch: Datos recibidos", data); // 5. Esto se ejecuta cuando la solicitud HTTP termina
    })
    .catch(error => {
        console.error("fetch: Error", error);
    });

// Promise: Crea una promesa que se resuelve después de 1 segundo
new Promise((resolve, reject) => {
    setTimeout(() => {
        resolve("Promise resuelta");
    }, 1000);
}).then(result => {
    console.log("Promise:", result); // 3. Esto se ejecuta después de 1 segundo
});

// setInterval: Ejecuta una función cada cierto intervalo de tiempo
let contador = 0;
const intervalo = setInterval(() => {
    contador++;
    console.log(`setInterval: Ejecutado ${contador} veces`); // 6, 7, 8... Esto se ejecuta cada 1.5 segundos

    if (contador === 3) {
        clearInterval(intervalo); // Detiene el intervalo después de 3 ejecuciones
        console.log("setInterval: Detenido"); // 9. Esto se ejecuta cuando el intervalo se detiene
    }
}, 1500);

console.log("Fin"); // 2. Esto se ejecuta de inmediato

```
1. **Código síncrono**:
    - `console.log("Inicio")` y `console.log("Fin")` se ejecutan de inmediato, en orden.
2. **Operaciones asíncronas**:
    - **`setTimeout`**: Programa una función para que se ejecute después de 2 segundos. No bloquea el código, por lo que el programa sigue ejecutándose.
    - **`fetch`**: Realiza una solicitud HTTP a una API. Como es una operación de red, toma tiempo en completarse. El código sigue ejecutándose mientras se espera la respuesta.
    - **`Promise`**: Crea una promesa que se resuelve después de 1 segundo. El `.then()` se ejecuta cuando la promesa se resuelve.
    - **`setInterval`**: Ejecuta una función cada 1.5 segundos. Después de 3 ejecuciones, se detiene con `clearInterval`.
        
3. **Orden de ejecución**:
    - Primero se ejecuta el código síncrono (`Inicio` y `Fin`).
    - Luego, las operaciones asíncronas se ejecutan en el orden en que terminan:
        - La `Promise` se resuelve después de 1 segundo.
        - El `setTimeout` se ejecuta después de 2 segundos.
        - El `fetch` se completa cuando llega la respuesta de la API (el tiempo depende de la red).
        - El `setInterval` se ejecuta cada 1.5 segundos hasta que se detiene.
