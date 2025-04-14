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
[[Web/Vue/Esencial/Components/Components]]

```ts
interface App {
  component(name: string): Component | undefined
  component(name: string, component: Component): this
}
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

```ts
import { createApp } from 'vue'

const app = createApp({
  /* ... */
})

// register (object directive)
app.directive('my-directive', {
  /* custom directive hooks */
})

// register (function directive shorthand)
app.directive('my-directive', () => {
  /* ... */
})

// retrieve a registered directive
const myDirective = app.directive('my-directive')
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
- Haga que un recurso sea inyectable en toda la aplicación llamando a **app.provide().**
