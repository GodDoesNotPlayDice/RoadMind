En el contexto de las aplicaciones Vue, un "**componible**" es una función que aprovecha la **Vue's Composition API** para encapsular y reutilizar la **lógica con estado.**

Al crear aplicaciones frontend, a menudo necesitamos reutilizar la lógica para tareas comunes. 
**Por ejemplo,** es posible que necesitemos formatear fechas en muchos lugares, por lo que extraemos una función reutilizable para ello. Esta función de formateador encapsula la lógica sin estado: toma alguna entrada e inmediatamente devuelve la salida esperada. Existen muchas bibliotecas para reutilizar la lógica sin estado, por ejemplo, lodash y date-fns, de las que quizás haya oído hablar.

**Por el contrario**, la lógica con estado implica gestionar un estado que cambia con el tiempo. Un ejemplo sencillo sería rastrear la posición actual del mouse en una página. En escenarios del mundo real, también podría tratarse de una lógica más compleja, como gestos táctiles o el estado de la conexión a una base de datos.


### Ventajas
- **Reutilización de lógica con estado.**
- **Compartir lógica entre componentes.**
- **Mantenimiento de la lógica en un solo lugar.**
- **Facilita la prueba de la lógica.**
### Ejemplo
Ejemplo de como trackear la posición del mouse.

```vue
<script setup>
import { ref, onMounted, onUnmounted } from 'vue'

const x = ref(0)
const y = ref(0)

function update(event) {
  x.value = event.pageX
  y.value = event.pageY
}

onMounted(() => window.addEventListener('mousemove', update))
onUnmounted(() => window.removeEventListener('mousemove', update))
</script>

<template>Mouse position is at: {{ x }}, {{ y }}</template>
```

La cosa es cuando necesitamos reutilizar la lógica con estado en múltiples componentes. **Aquí es donde entran en juego los composables.**

```js
  return { x, y }
```

Entonces se exporta y es posible ocuparlo en cualquier componente.

```vue
<script setup>
import { useMouse } from './mouse.js'

const { x, y } = useMouse()
</script>

<template>Mouse position is at: {{ x }}, {{ y }}</template>
```

### Composables con estado reactivo
El elemento componible `useMouse()` no acepta ningún argumento, así que echemos un vistazo a otro ejemplo que utiliza uno. Al realizar la recuperación de datos asíncronos, a menudo necesitamos manejar diferentes estados: carga, éxito y error

```vue
<script setup>
import { ref } from 'vue'

const data = ref(null)
const error = ref(null)

fetch('...')
  .then((res) => res.json())
  .then((json) => (data.value = json))
  .catch((err) => (error.value = err))
</script>

<template>
  <div v-if="error">Oops! Error encountered: {{ error.message }}</div>
  <div v-else-if="data">
    Data loaded:
    <pre>{{ data }}</pre>
  </div>
  <div v-else>Loading...</div>
</template>
```

Sería tedioso tener que repetir este patrón en cada componente que necesite recuperar datos. Vamos a extraerlo en un componible.

```js
// fetch.js
import { ref } from 'vue'

export function useFetch(url) {
  const data = ref(null)
  const error = ref(null)

  fetch(url)
    .then((res) => res.json())
    .then((json) => (data.value = json))
    .catch((err) => (error.value = err))

  return { data, error }
}
```

Ahora podemos usar este composable con parametros.
```vue
<script setup>
import { useFetch } from './fetch.js'

const { data, error } = useFetch('...')
</script>
```



