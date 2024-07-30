**Component Basic**: es la division de  la interfaz de usuario en partes independientes y reutilizables, y pensar en cada pieza de forma aislada. [Básico](#Component-basic).

**Component Registration**: Un componente de Vue debe "registrarse" para que Vue sepa dónde ubicar su implementación cuando se encuentre en una plantilla. Hay dos formas de registrar componentes: global y local. [Registro](#Component-registration).

## Component-basic

Normalmente vamos a definir un componente en un **`SFC`** cual usamos en un archivo **`.vue`**

```vue
<script setup>
import { ref } from 'vue'

const count = ref(0)
</script>

<template>
  <button @click="count++">You clicked me {{ count }} times.</button>
</template>
```

Pero si no, podemos definirlo en un archivo JS usando el objeto de **vue** por referencia, aunque no es lo mas correcto abusar de esto.

```js
import { ref } from 'vue'

export default {
  setup() {
    const count = ref(0)
    return { count }
  },
  template: `
    <button @click="count++">
      You clicked me {{ count }} times.
    </button>`
  // Can also target an in-DOM template:
  // template: '#my-template-element'
}
```



Para utilizar un componente secundario, debemos importarlo en el componente principal. Suponiendo que colocamos nuestro componente de contador dentro de un archivo llamado `ButtonCounter.vue`

```vue
<script setup>
import ButtonCounter from './ButtonCounter.vue'
</script>

<template>
  <h1>Here is a child component!</h1>
  <ButtonCounter />
</template>
```

Con `<script setup>`, los componentes importados se ponen automáticamente a disposición de la plantilla.

También es posible registrar globalmente un componente, poniéndolo a disposición de todos los componentes de una aplicación determinada sin tener que importarlo. 

Los pros y los contras del registro global frente al local se analizan en la sección dedicada al [Registro de componentes](#Component-registration)

### Passing Props
Los **`custom attributes`** personalizados que puede registrar en un componente para pasar un título a nuestro componente, debemos declararlo en la lista de accesorios que acepta este componente, usando la macro **`defineProps()`**

La mejor forma de hacerlo es con **`typescript`**, en el siguiente ejemplo tenemos que el **`setup`** trae por defecto lo que seria  **`defineProps()`** por lo que no hace falta importarlo, y es acá donde usamos la interfaz para definir todos los **props**.

#### SFC
```vue
<script setup lang="ts">
	interface Props {
		message: string;
		itsMine: boolean;
		image?: string;
}

defineProps<Props>();
</script>
```

En un ejemplo mas simple sin usar `interface` usando **`setup`** en la etiqueta podemos definir los props dentro.

```vue
<template>
	<h1 class="text-gray-300 text-3xl">{{ title }}</h1>
	<h2 class="text-gray-300 text-2xl">{{ subtitle }}</h2>
</template>

<script setup lang="ts">
	defineProps<{ title: string, subtitle: string }>();
</script>
```

Y por ultimo en **JS**
```vue
<template>
	<h1 class="text-gray-300 text-3xl">{{ title }}</h1>
	<h2 class="text-gray-300 text-2xl">{{ subtitle }}</h2>
</template>

<script setup lang="js">
	defineProps(['title', 'subtitle']);
</script>

```

#### TypeScript
En el archivo de **`typescript`** se utiliza **`defineComponent`** cual es el objeto para definir el componente.

```ts
import { defineComponent } from 'vue';
import { useCounter } from '@/composables/useCounter';

export default defineComponent({
	props: {
		value: {
		type: Number,
		required: true,
	},
},
setup(props) {
	const { counter, squareCounter } = useCounter(props.value);
	return { counter, squareCounter };
},

});
```

Luego en el **`SFC`** lo importamos como **`src`**.

```vue
<script lang="ts" src="./MyCounter"></script>
```

### Emits
Es para crear y emitir eventos que del Hijo ⇒ Padre.


Con el atributo **setup** en el `<script>` trae **`defineEmits`** y este maneja una tupla la cual se puede asignar métodos
```ts
const emits = defineEmits<{
	sendMessage: [text: string];
}>();

const sendMessage = () => {
	emits('sendMessage', message.value);
};

```

```vue
<input
type="text"
placeholder="Type your message..."
class="flex-1 border rounded-full px-4 py-2 focus:outline-none"
v-model="message"
@keypress.enter="sendMessage"
/>
```


#### TypeScript

```ts
export default {
  emits: ['enlarge-text'],
  setup(props, ctx) {
    ctx.emit('enlarge-text')
  }
}
```


## Component-registration

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

```vue
<ComponentA/>
<ComponentB/>
<ComponentC/>
```

#### Forma local
El registro local limita la disponibilidad de los componentes registrados únicamente al componente actual ademas hace que la relación de dependencia sea más explícita y es más amigable con **tree-shaking**.

Cuando se utiliza SFC con `<script setup>`, los componentes importados se pueden usar localmente sin registro

```vue
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
