## La instancia de la aplicación
La aplicación de Vue funciona mediante su función proveniente del objeto Vue.

```ts
import { createApp } from 'vue'

const app = createApp({
  /* root component options */
})
```
En vanilla o mas a profundidad así funciona `createApp()`
1)  **Argumento es el componente raíz.**
2)  **Argumento opcional son los accesorios que se pasarán al componente raíz.**

```js
function createApp(rootComponent: Component, rootProps?: object): App
```

**Sin `root component`**

```js
import { createApp } from 'vue'

const app = createApp({
  /* root component options */
})
```

**Con `root component`**

```js
import { createApp } from 'vue'
import App from './App.vue'

const app = createApp(App)
```

Cada aplicación requiere un **"componente raíz"** que puede contener otros componentes como elementos secundarios.
```ts
const app = createApp({
	setup() {
		console.log('Hello World');
	}
})
```
 
> Tiene un SSR pero no tienen muchas funcionalidades como el `createApp()`.
> `createSSRApp()` 

If you are using **Single-File Components**, we typically import the root component from another file:
```ts
import { createApp } from 'vue'
// import the root component App from a single-file component.
import App from './App.vue'

const app = createApp(App)
	```



Create  app tiene un montón de métodos para usar.  [[All methods]]
```js
app.component('TodoDeleteButton', TodoDeleteButton)
app.config.errorHandler = (err) => {
  /* handle error */
}
```

## Montando la App
Una instancia de aplicación no representará nada hasta que se llame a su método **`.mount()`**.

```html
<div id="app"></div>
```

```js
import { createApp } from 'vue'
const app = createApp(/* ... */)

app.mount('#app')
```

El contenido del componente raíz de la aplicación se representará dentro del elemento contenedor. **El elemento contenedor en sí no se considera parte de la aplicación.**

Siempre se debe llamar al método **`.mount()`** después de realizar todas las configuraciones de la aplicación y los registros de activos, esto se refiere que es lo ultimo método que se usa.


**`mount()`**: Espera un argumento "contenedor", que puede ser un elemento **DOM real o una cadena selectora.**

Si el componente tiene una plantilla o una función de representación definida, reemplazará cualquier nodo DOM existente dentro del contenedor.

De lo contrario, si el compilador en tiempo de ejecución está disponible, el HTML interno del contenedor se utilizará como plantilla.

```ts
interface App {
  mount(rootContainer: Element | string): ComponentPublicInstance
}
```

**Cadena selectora**: Llevado por la id en la etiqueta.
```js
import { createApp } from 'vue'
const app = createApp(/* ... */)

app.mount('#app')
```

**Cadena selectora**: Variable que tiene el elemento del DOM.
```js
app.mount(document.body.firstChild)
```

Es posible tener multiples instancias.

```js
const app1 = createApp({
  /* ... */
})
app1.mount('#container-1')

const app2 = createApp({
  /* ... */
})
app2.mount('#container-2')
```

### `app.unmount()`

Desmonta una instancia de aplicación montada, lo que activa los enlaces del ciclo de vida de desmontaje para todos los componentes en el árbol de componentes de la aplicación.

```ts
interface App {
  unmount(): void
}
```


