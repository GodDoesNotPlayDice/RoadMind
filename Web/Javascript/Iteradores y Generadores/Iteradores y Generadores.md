## ¿Que es un iterador?
Imagina que tienes una lista de tareas (como un array de números: `[1, 2, 3]`). Un **iterador** es como un "dedo electrónico" que **señala un elemento de la lista**, te lo entrega, y luego avanza al siguiente.
### Caracteristicas clave
**Protocolo del Iterador**: Es una regla que dice:  "Para ser iterador, debes tener un método `next()` que devuelva un objeto `{ value: valorActual, done: siTerminó }`".

**Ejemplo con un Array** (ya es iterable por defecto):

```js
const numeros = [1, 2, 3];
const iterador = numeros[Symbol.iterator](); // Obtiene el iterador del array

console.log(iterador.next()); // { value: 1, done: false }
console.log(iterador.next()); // { value: 2, done: false }
console.log(iterador.next()); // { value: 3, done: false }
console.log(iterador.next()); // { value: undefined, done: true } → ¡Fin!
```

#### ¿Para qué sirve?
- Permite recorrer elementos **uno por uno**, sin necesidad de saber cómo está estructurada la lista internamente.
- Funciona con `for...of`, `[...array]`, y otras estructuras de JavaScript.


## ¿Que es un generador?
Permite recorrer elementos **uno por uno**, sin necesidad de saber cómo está estructurada la lista internamente.

Funciona con `for...of`, `[...array]`, y otras estructuras de JavaScript.

### Características clave
- Se define con `function*`.
- Usa `yield` para "entregar" un valor y **pausar** la ejecución.

**Ejemplo básico**
```js
function* generadorDeColores() {
  yield "rojo";    // Entrega "rojo" y pausa
  yield "verde";   // Entrega "verde" y pausa
  yield "azul";    // Entrega "azul" y pausa
}

const gen = generadorDeColores();
console.log(gen.next()); // { value: 'rojo', done: false }
console.log(gen.next()); // { value: 'verde', done: false }
console.log(gen.next()); // { value: 'azul', done: false }
console.log(gen.next()); // { value: undefined, done: true }
```

#### ¿Para qué sirve?
- Crear secuencias **infinitas** (como números aleatorios, IDs únicos, etc.).
- Simplificar la creación de iteradores complejos.
- Controlar el flujo de ejecución paso a paso.

## Diferencia Clave

| **Iterador**                                        | **Generador**                                                    |
| --------------------------------------------------- | ---------------------------------------------------------------- |
| Tú defines manualmente cómo avanza (`next()`).      | JavaScript maneja el `next()` automáticamente gracias a `yield`. |
| Útil para estructuras personalizadas (ej: árboles). | Ideal para secuencias dinámicas o infinitas (ej: Fibonacci).     |
## Ejemplo detallado: Generador Infinito (Números pares)

```js
function* numerosPares() {
  let numero = 0;
  while (true) { // ¡Bucle infinito!
    yield numero;
    numero += 2;
  }
}

const pares = numerosPares();
console.log(pares.next().value); // 0
console.log(pares.next().value); // 2
console.log(pares.next().value); // 4
// ¡Nunca termina! Pero como se usa "bajo demanda", no bloquea el programa.
```

## ¿Cómo se relacionan?
**Los generadores son iteradores automáticos**: Cuando creas un generador, JavaScript internamente implementa el método `next()` por ti.

Puedes usar generadores en `for...of`:

```js
function* generadorDeFrutas() {
  yield "🍎";
  yield "🍌";
  yield "🍇";
}

for (const fruta of generadorDeFrutas()) {
  console.log(fruta); // 🍎, 🍌, 🍇
}
```

**Lazy Evaluation**: Generar valores solo cuando se necesitan (ej: procesar archivos grandes línea por línea).

**Controlar flujos complejos**: Como recorrer un árbol de decisiones en un juego.

**Async/Await**: Los generadores fueron la base para implementar `async/await` en JavaScript. [[Async Await]]

