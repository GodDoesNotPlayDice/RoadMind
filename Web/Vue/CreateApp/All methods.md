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


