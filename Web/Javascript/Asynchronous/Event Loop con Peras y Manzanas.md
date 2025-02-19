El **Event Loop** es un mecanismo en JavaScript que permite manejar operaciones **asíncronas** sin bloquear la ejecución del código. Aquí está cómo funciona paso a paso

### JavaScript es la cocina
- JavaScript es **monohilo**, es decir, solo puede hacer una cosa a la vez (como tener una sola persona en la cocina).
- Pero en la cocina tienes varias tareas: pelar peras, cortar manzanas, hornear galletas, etc. Algunas tareas toman más tiempo que otras.

### Event Loop es el Chef
El Event Loop es como un chef muy organizado que decide qué hacer en cada momento. Aquí está cómo funciona:

#### Tareas Síncronas (las que hace de inmediato)
- Pelar una manzana es una tarea rápida. El chef la hace de inmediato y la tarea se termina.
- En JavaScript, esto sería como ejecutar una función normal, como sumar dos números.

#### Tareas Asíncronas (las que toman tiempo)
- Hornear galletas es una tarea que toma tiempo. El chef no puede quedarse esperando a que las galletas se horneen, porque tiene otras cosas que hacer.
- Entonces, el chef pone las galletas en el horno y **continúa con otras tareas** mientras las galletas se hornean.
- En JavaScript, esto sería como usar `setTimeout`, `fetch`, o `Promise`. Estas tareas se "dejan en segundo plano" y el código sigue ejecutándose.

#### La cola de Tareas
- Cuando las galletas están listas, el horno hace un _ding_ para avisar al chef.
- El chef no deja todo lo que está haciendo para sacar las galletas de inmediato. En su lugar, **anota en una lista** que las galletas están listas y las sacará cuando termine la tarea actual.
- En JavaScript, esto es la **cola de mensajes** (o **callback queue**). Las tareas asíncronas terminadas (como el _ding_ del horno) se ponen en esta cola para ser procesadas.

#### El Event Loop (el chef revisando la lista):
- El chef siempre está revisando si hay algo en su lista de tareas pendientes (la cola de mensajes).
- Cuando termina de pelar una manzana o cortar una pera, **revisa la lista** para ver si hay algo más que hacer (como sacar las galletas del horno).
- En JavaScript, el Event Loop revisa constantemente si hay callbacks en la cola de mensajes. Si la pila de llamadas (call stack) está vacía, toma el siguiente callback de la cola y lo ejecuta.

### Ejemplo en codigo

```js
console.log("Pelar manzana"); // Tarea síncrona (se hace de inmediato)

setTimeout(() => {
    console.log("Sacar galletas del horno"); // Tarea asíncrona (se hace después)
}, 2000);

console.log("Cortar peras"); // Tarea síncrona (se hace de inmediato)
```
