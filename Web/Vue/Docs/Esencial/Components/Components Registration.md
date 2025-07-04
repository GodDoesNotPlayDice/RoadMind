#### Forma Global
Si bien es conveniente, el registro global tiene algunos inconvenientes.

- El registro global evita que los sistemas de compilación eliminen componentes no utilizados **(también conocido como "sacudida de árboles")**. Si registra globalmente un componente pero al final no lo utiliza en ninguna parte de su aplicación, **seguirá incluido en el paquete final.**
- El registro global hace que las **relaciones de dependencia** sean menos explícitas en aplicaciones grandes.
	- Hace que sea difícil localizar la implementación de un componente secundario desde un componente principal que lo utiliza. 
	- Esto puede afectar la mantenibilidad a largo plazo de manera similar al uso de demasiadas variables globales.


Podemos hacer que los componentes estén disponibles globalmente en la aplicación Vue actual usando el método **`.component()`**

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

Usando **SFC** registrará los archivos **`.vue`** importados

```js
import MyComponent from './App.vue'

app.component('MyComponent', MyComponent)
```

El método **`.component()`** se puede encadenar

```js
app
  .component('ComponentA', ComponentA)
  .component('ComponentB', ComponentB)
  .component('ComponentC', ComponentC)
```

Los componentes registrados globalmente se pueden utilizar en la plantilla de cualquier componente dentro de esta aplicación.

```html
<ComponentA/>
<ComponentB/>
<ComponentC/>
```

#### Forma local
El registro local limita la disponibilidad de los componentes registrados únicamente al componente actual ademas hace que la relación de dependencia sea más explícita y es más amigable con **tree-shaking**.

Cuando se utiliza SFC con `<script setup>`, los componentes importados se pueden usar localmente sin registro

```html
<script setup>
import ComponentA from './ComponentA.vue'
</script>

<template>
  <ComponentA />
</template>
```

Sin `setup` se debe definir el export del componente.

```ts
import ComponentA from './ComponentA.js'

export default {
  components: {
    ComponentA
  },
  setup() {
    // ...
  }
}
```

Tener en cuenta que los componentes registrados localmente no están disponibles también en componentes descendientes. En este caso, **`Component A`** estará disponible únicamente para el componente actual, **no para ninguno de sus componentes secundarios o descendientes.**

Por ultimo los componentes deben estar registrados en **Pascal-Case**, el porque es
1) Los nombres de **PascalCase** son identificadores de JavaScript válidos. Esto facilita la importación y el registro de componentes en JavaScript. También ayuda a los IDE con el autocompletado.
2) `<PascalCase />` hace que sea más obvio que se trata de un componente de Vue en lugar de un elemento HTML nativo en las plantillas. También diferencia los componentes de Vue de los elementos personalizados (componentes web).

Por suerte también se puede registrar en **kebab-case**
`<my-component >`
