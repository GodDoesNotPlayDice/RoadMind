## Todos los métodos de `createApp()`

```js
import { createApp } from 'vue';
import App from './App.vue';
import VueRouter from 'vue-router';
import MyComponent from './MyComponent.vue';

const app = createApp(App);

// Uso de un plugin
app.use(VueRouter);

// Registro de un componente global
app.component('MyComponent', MyComponent);

// Registro de una directiva global
app.directive('focus', {
  mounted(el) {
    el.focus();
  }
});

// Añadir un mixin global
app.mixin({
  created() {
    console.log('Global Mixin');
  }
});

// Proveer una propiedad global
app.provide('myKey', 'myValue');

// Montar la aplicación
app.mount('#app');

// Acceder a la versión de Vue
console.log(app.version);
```


### `app.component()`
Registra un componente global si se pasa una cadena de nombre y una definición de componente, o recupera uno ya registrado si solo se pasa el nombre.

```ts
interface App {
  component(name: string): Component | undefined
  component(name: string, component: Component): this
}
```

```ts
import { createApp } from 'vue'

const app = createApp({})

// register an options object
app.component('my-component', {
  /* ... */
})

// retrieve a registered component
const MyComponent = app.component('my-component')
```

### `app.directive()`
Registra una directiva personalizada global si se pasa una cadena de nombre y una definición de directiva, o recupera una ya registrada si solo se pasa el nombre.

Es muy similar a los **custom hooks de React.**

```ts
interface App {
  directive(name: string): Directive | undefined
  directive(name: string, directive: Directive): this
}
```

Suponiendo que no haya hecho clic en ninguna otra parte de la página, la entrada anterior debería tener enfoque automático.

Esta directiva es más útil que el atributo de enfoque automático **porque no solo funciona al cargar la página, sino que también funciona cuando Vue inserta dinámicamente el elemento.**
```vue
<script setup>
// enables v-focus in templates
const vFocus = {
  mounted: (el) => el.focus()
}
</script>

<template>
  <input v-focus />
</template>
```

En `script setup`, cualquier variable **camelCase** que comience con el prefijo v se puede utilizar como directiva personalizada.

En el ejemplo anterior, **vFocus** se puede utilizar en la plantilla como **v-focus**.

Si no se utiliza `<script setup>`, las directivas personalizadas se pueden registrar usando las directivas.

```js
export default {
  setup() {
    /*...*/
  },
  directives: {
    // enables v-focus in template
    focus: {
      /* ... */
    }
  }
}
```

También es común registrar globalmente directivas personalizadas a **nivel de aplicación**

```js
const app = createApp({})

// make v-focus usable in all components
app.directive('focus', {
  /* ... */
})
```
### `app.use()`
Los **complementos** son código autónomo que generalmente agrega funcionalidad a nivel de aplicación a Vue. 

Un **complemento** se define como un objeto que expone un método install() o simplemente una función que actúa como la función de instalación en sí.

La función de instalación **recibe la instancia de la aplicación junto con opciones adicionales pasadas a app.use()**

```ts
const myPlugin = {
  install(app, options) {
    // configure the app
  }
}
```

No existe un alcance estrictamente definido para un complemento.

- Registre uno o más componentes globales o directivas personalizadas con **app.component() y app.directive().**
- Haga que un recurso sea inyectable en toda la aplicación llamando a app.provide().