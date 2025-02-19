Una **Promise** es un objeto que representa el resultado eventual (éxito o fracaso) de una operación asíncrona. Una promesa puede estar en uno de los siguientes estados:
1. **Pending (Pendiente)**: Estado inicial, la operación aún no se ha completado.
2. **Fulfilled (Cumplida)**: La operación se completó con éxito.
3. **Rejected (Rechazada)**: La operación falló.

Una vez que una promesa se cumple o se rechaza, no puede cambiar de estado.

Estas a menudo van de la mano con [[Async Await]]

## Sintaxis básicas
Una promesa se crea usando el constructor `Promise`, que recibe una función con dos parámetros: `resolve` y `reject`.

```js
 const miPromesa = new Promise((resolve, reject) => {
  // Lógica asíncrona
  if (/* operación exitosa */) {
    resolve("Éxito"); // La promesa se cumple
  } else {
    reject("Error"); // La promesa se rechaza
  }
});
```

## Métodos de una Promise
Las promesas tienen métodos para manejar el resultado una vez que se resuelven:
1. **`.then()`**: Se ejecuta cuando la promesa se cumple.
2. **`.catch()`**: Se ejecuta cuando la promesa se rechaza.
3. **`.finally()`**: Se ejecuta siempre, sin importar si la promesa se cumple o se rechaza.

```js
miPromesa
  .then((resultado) => {
    console.log("Promesa cumplida:", resultado);
  })
  .catch((error) => {
    console.error("Promesa rechazada:", error);
  })
  .finally(() => {
    console.log("La promesa ha terminado (éxito o fracaso).");
  });
```

## Ejemplo practicó
Supongamos que queremos simular una operación asíncrona, como una solicitud a un servidor:

```js
const obtenerDatos = new Promise((resolve, reject) => {
  setTimeout(() => {
    const exito = true; // Simulamos si la operación tuvo éxito
    if (exito) {
      resolve("Datos recibidos correctamente.");
    } else {
      reject("Error al obtener los datos.");
    }
  }, 2000); // Simulamos un retraso de 2 segundos
});

obtenerDatos
  .then((mensaje) => {
    console.log(mensaje);
  })
  .catch((error) => {
    console.error(error);
  });
```

## Encadenamiento de Promesas
Puedes encadenar múltiples promesas usando `.then()`. Cada `.then()` recibe el resultado del anterior y puede devolver una nueva promesa.

```js
const primeraPromesa = new Promise((resolve) => {
  setTimeout(() => resolve(10), 1000);
});

primeraPromesa
  .then((numero) => {
    console.log("Primer then:", numero);
    return numero * 2; // Devuelve un valor
  })
  .then((numero) => {
    console.log("Segundo then:", numero);
    return new Promise((resolve) => resolve(numero + 5)); // Devuelve otra promesa
  })
  .then((numero) => {
    console.log("Tercer then:", numero);
  });
```

## Manejo de errores
Puedes usar `.catch()` para manejar errores en cualquier punto del encadenamiento:

```js
const promesaConError = new Promise((resolve, reject) => {
  setTimeout(() => reject("Algo salió mal"), 1000);
});

promesaConError
  .then((resultado) => {
    console.log(resultado);
  })
  .catch((error) => {
    console.error("Error:", error);
  });
```

## `Promise.all()`

**Propósito**: Ejecuta un conjunto de promesas en paralelo y espera a que **todas** se resuelvan.

**Comportamiento**:
- Si **todas** las promesas se cumplen, devuelve un array con los resultados en el mismo orden.
- Si **alguna** promesa es rechazada, inmediatamente se rechaza con el error de la primera promesa que falló.

```js
const promesa1 = Promise.resolve(1);
const promesa2 = Promise.resolve(2);
const promesa3 = new Promise((resolve) => setTimeout(() => resolve(3), 1000));

Promise.all([promesa1, promesa2, promesa3])
  .then((resultados) => {
    console.log("Todos los resultados:", resultados); // [1, 2, 3]
  })
  .catch((error) => {
    console.error("Al menos una promesa falló:", error);
  });
```

## `Promise.allSettled()`

**Propósito**: Ejecuta un conjunto de promesas en paralelo y espera a que **todas** se resuelvan o se rechacen, sin importar el resultado.

**Comportamiento**:
- Devuelve un array de objetos que describen el resultado de cada promesa.
- Cada objeto tiene una propiedad `status` (`fulfilled` o `rejected`) y, dependiendo del estado, `value` (si se cumplió) o `reason` (si se rechazó).

```js
const promesa1 = Promise.resolve(1);
const promesa2 = Promise.reject("Error en promesa2");
const promesa3 = new Promise((resolve) => setTimeout(() => resolve(3), 1000));

Promise.allSettled([promesa1, promesa2, promesa3])
  .then((resultados) => {
    console.log("Resultados:", resultados);
    /*
    [
      { status: 'fulfilled', value: 1 },
      { status: 'rejected', reason: 'Error en promesa2' },
      { status: 'fulfilled', value: 3 }
    ]
    */
  });
```


## `Promise.race()`

**Propósito**: Ejecuta un conjunto de promesas en paralelo y devuelve el resultado de la primera promesa que se resuelva (ya sea cumplida o rechazada).

**Comportamiento**:
- La promesa devuelta toma el estado (cumplida o rechazada) de la primera promesa que se resuelva.

```js
const promesa1 = new Promise((resolve) => setTimeout(() => resolve(1), 2000));
const promesa2 = new Promise((resolve) => setTimeout(() => resolve(2), 1000));
const promesa3 = new Promise((_, reject) => setTimeout(() => reject("Error"), 500));

Promise.race([promesa1, promesa2, promesa3])
  .then((resultado) => {
    console.log("Primera promesa en resolverse:", resultado);
  })
  .catch((error) => {
    console.error("Primera promesa en rechazarse:", error); // "Error"
  });
```

## `Promise.any()`

**Propósito**: Ejecuta un conjunto de promesas en paralelo y devuelve el resultado de la **primera promesa que se cumpla** (ignora los rechazos hasta que haya una promesa cumplida).

**Comportamiento**:
- Si **alguna** promesa se cumple, devuelve su valor.
- Si **todas** las promesas son rechazadas, devuelve un error agregado (`AggregateError`).

```js
const promesa1 = new Promise((_, reject) => setTimeout(() => reject("Error 1"), 1000));
const promesa2 = new Promise((resolve) => setTimeout(() => resolve(2), 500));
const promesa3 = new Promise((_, reject) => setTimeout(() => reject("Error 3"), 2000));

Promise.any([promesa1, promesa2, promesa3])
  .then((resultado) => {
    console.log("Primera promesa cumplida:", resultado); // 2
  })
  .catch((error) => {
    console.error("Todas las promesas fueron rechazadas:", error);
  });
```

## `Promise.resolve()`

**Propósito**: Crea una promesa que ya está **cumplida** con un valor específico.

**Comportamiento**:
- Devuelve una promesa que se resuelve inmediatamente con el valor proporcionado.

```js
const promesa = Promise.resolve("Éxito");

promesa.then((resultado) => {
  console.log(resultado); // "Éxito"
});
```

## `Promise.reject()`

**Propósito**: Crea una promesa que ya está **rechazada** con una razón específica.

**Comportamiento**:
- Devuelve una promesa que se rechaza inmediatamente con la razón proporcionada.

```js
const promesa = Promise.reject("Error");

promesa.catch((error) => {
  console.error(error); // "Error"
});
```


## Resumen de métodos de las promesas.

| Método                         | Descripción                                                            |
| ------------------------------ | ---------------------------------------------------------------------- |
| `Promise.all(iterable)`        | Espera a que todas las promesas se cumplan o una sea rechazada.        |
| `Promise.allSettled(iterable)` | Espera a que todas las promesas se resuelvan (cumplidas o rechazadas). |
| `Promise.race(iterable)`       | Devuelve el resultado de la primera promesa que se resuelva.           |
| `Promise.any(iterable)`        | Devuelve el resultado de la primera promesa que se cumpla.             |
| `Promise.resolve(valor)`       | Crea una promesa cumplida con un valor específico.                     |
| `Promise.reject(razón)`        | Crea una promesa rechazada con una razón específica.                   |
