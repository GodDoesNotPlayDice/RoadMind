**Component Basic**: es la division de  la interfaz de usuario en partes independientes y reutilizables, y pensar en cada pieza de forma aislada.

**Component Registration**: Un componente de Vue debe "registrarse" para que Vue sepa dónde ubicar su implementación cuando se encuentre en una plantilla. Hay dos formas de registrar componentes: global y local. [[Components Registration]]

1. [Passing Props](#Passing-Props)
2. [Emits](#Emits)
3. [Slots](#Slots)
4. [Dynamic Components](#Dynamic-Components)

Normalmente vamos a definir un componente en un **`SFC`** cual usamos en un archivo **`.vue`**

```html
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

```html
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

### Passing-Props
Los **`custom attributes`** personalizados que puede registrar en un componente para pasar un título a nuestro componente, debemos declararlo en la lista de accesorios que acepta este componente, usando la macro **`defineProps()`**

La mejor forma de hacerlo es con **`typescript`**, en el siguiente ejemplo tenemos que el **`setup`** trae por defecto lo que seria  **`defineProps()`** por lo que no hace falta importarlo, y es acá donde usamos la interfaz para definir todos los **props**.

#### SFC
```html
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

```html
<template>
	<h1 class="text-gray-300 text-3xl">{{ title }}</h1>
	<h2 class="text-gray-300 text-2xl">{{ subtitle }}</h2>
</template>

<script setup lang="ts">
	defineProps<{ title: string, subtitle: string }>();
</script>
```

Y por ultimo en **JS**
```html
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

```html
<script lang="ts" src="./MyCounter"></script>
```

### Emits
Es para crear y emitir eventos que del Hijo ⇒ Padre.


Con el atributo **setup** en el `<script>` trae **`defineEmits`** y este maneja una tupla la cual se puede asignar métodos

```html
<div class="grid grid-cols-2 h-screen">
	<div class="bg-green-600 h-full w-full flex justify-center items-center">
		<p class="text-2xl font-bold text-white">{{ n_val }}</p>
	</div>
	<RandomValue
	@send-random-number="getRandomNumber"
	class="bg-green-800 h-full w-full flex justify-center items-center">
	</RandomValue>
</div>

<script lang=ts setup>
import { ref } from 'vue'
const n_val = ref(0)

const getRandomNumber = (n: number) => {
  n_val.value = n
}

</script>
```

```html
<template>
	<div>
		<button class="cursor-pointer" @click="sendRandomNumber">
			<h1 class="font-bold text-white">Uso del defineEmits</h1>
			<p class="text-2xl font-bold text-white">Clickeame</p>
		</button>
	</div>
</template>


<script lang="ts" setup>
import { ref } from 'vue'
const emit = defineEmits<{
sendRandomNumber: [value: number]
}>()


const sendRandomNumber = () => {
const randomNumber = ref(Math.random())
emit('sendRandomNumber', randomNumber.value)
}
</script>

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

### Slots

Al igual que con los elementos HTML, suelen ser útil poder pasar contenido a un componente.

Lo que hace slot es generar una etiqueta custom para poder pasar **lo que sea** por una etiqueta HTML mas de los [[Slots]]

**`App.vue`**
```html
<script setup>
import AlertBox from './AlertBox.vue'
</script>

<template>
	<AlertBox>
		Something bad happened.
	</AlertBox>
</template>
```

**`AlertBox.vue`**
```html
<template>

	<div class="alert-box">
		<strong>Error!</strong>
		<br/>	
		<slot />
	</div>
</template>
```


### Dynamic-Components
En vue existen los componentes cuales nos servirán para poder rederizar ciertos componentes si necesidad de tener los tres en tres etiquetas diferentes.

En este ejemplo podemos apreciar como funciona el **atributo `is`** cual sirve para indicar **si es** o **no es**, en este caso tenemos **3 SFC o Components** los cuales son importados y agregados al objeto **`tabs`** y un **`currentTab`** cual sera una variable **reactiva**, luego se generan **3 botones** los cuales son **`Home, Posts, Archive`** cuales se comportaran como **`tabs`** y estos irán cambiando dependiendo de la variable **reactiva** que es actualizada al **Tab** en el momento de hacer click.  

Y por ultimo en la etiqueta **`componnet`** usar **`:is`** mas **`tabs[currentTab]`** y tener la plantilla del componente seleccionado.

```html
<script setup>
import Home from './Home.vue'
import Posts from './Posts.vue'
import Archive from './Archive.vue'
import { ref } from 'vue'

const currentTab = ref('Home')
const tabs = {
Home,
Posts,
Archive
}
</script>

<template>
	<div class="demo">
	
	<button
	v-for="(_, tab) in tabs"
	:key="tab"
	:class="['tab-button', { active: currentTab === tab }]"
	@click="currentTab = tab">	
	{{ tab }}
	
	</button>
	
	<component :is="tabs[currentTab]" class="tab"></component>
	
	</div>

</template>
```

Este es un ejemplo muy bueno y ademas se puede relacionar mucho con [[Ciclo de vida]]
