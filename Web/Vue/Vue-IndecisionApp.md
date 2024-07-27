```bash
npm create vue@latest # TS, Eslint, Devtools.
```

## Estructura del proyecto
### Estructura
```
.vscode/
node_modules/
public/
src/
├── .eslintrc.cjs
├── .gitignore
├── .prettierrc.json
├── env.d.ts
├── index.html
├── package-lock.json
├── package.json
├── README.md
├── tsconfig.app.json
├── tsconfig.json
├── tsconfig.node.json
├── tsconfig.vitest.json
├── vite.config.ts
└── vitest.config.ts

```

### Descripciones
**vitest.config.ts**: Archivo de configuración de como trabaja **vite**.
**tsconfig.node.json** : Archivo de configuración de node.
**tsconfig.json**: Archivo de configuración global de la App.
**tsconfig.app.json**: Archivo de configuración de la App.
**README.md**: Archivo que proporciona información esencial sobre un proyecto de software.
**package.json**: Todas las librerías que están en el proyecto.
**prettierrc.json**: Archivo de formatter para que todos tengamos el mismo orden.
**.gitignore**: Archivo para ignorar el git de algunos archivos.
**.eslintrc.cjs**: Reglas para hacer o seguir los componentes de Vue y seguir las buenas practicas.
**src**: El source donde se trabaja vienen todos los archivos de desarrollo.
**main.ts**: Archivo principal de la app.
**assets**: Recursos de la aplicación.
**public**: Recursos estáticos.
**.vscode**: Config sobre vscode en el proyecto.


## Single File Component (SFC)
Los SFC permiten definir un componente en un solo archivo, generalmente con la extensión `.vue`. Estos archivos agrupan el código **HTML, CSS y JavaScript** necesarios para el componente en una estructura organizada y modular. [Syntax](https://vuejs.org/api/sfc-spec.html#sfc-syntax-specification)

**Template (`<template>`)**: Aquí se define la estructura HTML del componente. Esta sección describe cómo se verá el componente en la interfaz de usuario.
- En profundidad los contenidos se extraerán y pasarán a **`@vue/compiler-dom`**, se pre-compilarán en funciones de renderizado de **JavaScript** y se adjuntarán al componente exportado como su opción de renderizado.

**Script (`<script>`)**: En esta sección se escribe el código JavaScript que controla la lógica del componente. Aquí es donde se manejan los datos, métodos y ciclo de vida del componente, por ultimo si queremos exportar código debe ser mediante un componente.
- **`lang`**: Define el lenguaje del **`script`**, puede ser JS o TS
- **`setup`**: Se puede agregar para tener el inicializador de Vue.

**Style (`<style>`)**: Esta sección contiene los estilos CSS específicos para el componente. Puede ser opcional y puede incluirse con un atributo `scoped` .
- **`scoped`**: Es para que los estilos solo se apliquen al componente actual.

```vue
<template>
	<section>
		<div>
			<h3>Counter: {{ counter }}</h3>
			<h4>Square: {{ squareCounter }}</h4>
		</div>
		<div>
			<button @click="counter++">+1</button>
			<button @click="counter--">-1</button>
		</div>@
	</section>
</template>

<script lang="ts" setup>
	import { computed, ref } from 'vue';
	
	const counter = ref(10);
	const squareCounter = computed(() => counter.value * counter.value);
</script>
```


### Computed
En este caso **`counter`** cambie de valor **`squareCounter`** también lo hará ya que depende de la variable reactiva **`counter`**.

```vue
<script lang="ts" setup>
	import { computed, ref } from 'vue';
	
	const counter = ref(10);
	const squareCounter = computed(() => counter.value * counter.value);
</script>
```

### Pre-procesadores
Como bien se menciono antes se pueden agregar atributo a las etiquetas para definir un **pre-procesador** con **`lang`**

```vue

<template lang="pug">
p {{ msg }}
</template>

<script lang="ts">
  // use TypeScript
</script>

<style lang="scss">
  $primary-color: #333;
  body {
    color: $primary-color;
  }
</style>
```

## Componentes
Los componentes en Vue no tienen nada de diferente a componentes en otros frameworks pero si algo especial es con el **linter** cual por reglas de Vue no podemos hacer un componente con una sola palabra tienen que ser dos.
[Multi-word](https://eslint.vuejs.org/rules/multi-word-component-names.html) ⇒ [[Vue-Rules]]

Estructura en carpeta.
```
src/
├── components/
	├── MyComponent.vue
	Vue.app
```

**`App.vue`**
```vue
<template>
	<h1>Nice</h1>
	<hr>
	<MyCounter />
</template>

<script lang="ts" setup>
import MyCounter from './components/MyCounter.vue';
</script>
```

Dentro de los componentes un detalle bien importante cuando se divide la lógica. esto es un poco mas complejo ya que usamos [Composables](#Composables) para llamar cierta lógica.

Esto respeta un poco mas el orden de los componentes ya que podemos separar la logica en un archivo **typescript** y otro en **.vue**
```
src/
├── components/
		MyComponent/
		├── MyComponent.ts
		├── MyComponent.vue
	Vue.app
```

**`src/components/mycomponent`**

**`MyComponent.ts`**
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
		return {
			counter, squareCounter,
		};
	},
});
```

**`MyComponent.vue`**
```vue
<template>
	<section>
		<div>
			<h3>Counter: {{ counter }}</h3>
			<h4>Square: {{ squareCounter }}</h4>
		</div>
		<div>
			<button @click="counter++">+1</button>
			<button @click="counter--">-1</button>
		</div>
	</section>
</template>

<script lang="ts" src="./MyComponent"></script>
```

**`src`**

**`App.vue`**
```vue
<template>
  
	<MyComponent :value="5" />

</template>

<script lang="ts" setup>

import MyComponent from './components/MyComponent/MyComponent';

</script>

```

## Recibir proprieties 
Tenemos dos según la documentación, **`defineProps()`** y **`defineEmits()`**

### Define Props
Es para recibir proprieties del Padre ⇒ Hijo.
```js
const props = defineProps({
  foo: String
})
```

#### Ejemplo en la App.
Tenemos en nuestra **`App.vue`** el componente con un **`bind`** cual pasa por valor un numero.
```vue
<MyCounter :value="5"/>
```

Se debe capturar ese valor que es pasado, por lo que se usa **`defineProps()`** y esta definimos el **`parametro : valor`** , que pasa con este parámetro que lo **TS** lo toma opcional. 
```js
const props = defineProps({
	value: Number, // readonly value?: number | undefined;  
});
```

Por lo que para no tener inconvenientes podemos hacerlo obligatorio de esta forma.
```js
const props = defineProps({
	value: { // readonly value: number;
		type: Number,
		required: true,
	},
});
```

Para **typescript** se puede usar los genéricos para crear el objeto en el mismo prop.
```ts
const props = defineProps<{ value: number }>();
```

O podemos crear una **Interface**.
```ts
interface Props {
	value: number;
}

const props: Props = defineProps<Props>();
```

La forma antigua y larga que se usaba en **Options API**.
```vue
<script lang="ts">
	import { computed, defineComponent, ref } from 'vue';
	
	export default defineComponent({
		props: {
			value: {
			type: Number,
			required: true,
			},
			text: {
			type: String,
			required: true,
			},
		},
		setup(props) {
			const counter = ref(props.value);
			const squareCounter = computed(() => counter.value * counter.value);
			return {
			counter,
			squareCounter,
			};
		},
	});
</script>
```


### Define Emits
Es para crear y emitir eventos que del Hijo ⇒ Padre.
```js
const emit = defineEmits(['change', 'delete'])
```


## Tree shaking
Tree shaking, también conocido como "depuración del árbol de dependencias", es un término que proviene de la idea de sacudir un árbol para eliminar las hojas muertas. En el contexto del desarrollo de software, significa eliminar el código que no se usa de la aplicación. Esta técnica es particularmente útil en aplicaciones de JavaScript modernas, donde las librerías y frameworks pueden ser bastante grandes.

### Beneficios de Tree Shaking

- **Reducción del Tamaño del Bundle**: Al eliminar el código no utilizado, el tamaño del bundle que se entrega al navegador es más pequeño, lo que resulta en tiempos de carga más rápidos.
- **Mejora del Rendimiento**: Un bundle más pequeño significa menos código para analizar y ejecutar, lo que mejora el rendimiento general de la aplicación.
- **Optimización Automática**: Con herramientas de construcción modernas, la optimización a través de tree shaking es automática, lo que facilita a los desarrolladores mantener sus aplicaciones eficientes sin necesidad de hacer optimizaciones manuales.

## Composables 
Las Composable Functions son funciones que puedes definir para encapsular lógica reactiva y re-utilizable, permitiéndote compartir esta lógica entre diferentes componentes.

Se llaman "composables" porque están diseñadas para ser combinadas y reutilizadas en la composición de tus componentes.

### Características Principales

1. **Reutilización de Lógica**: Permiten extraer y compartir lógica de estado entre componentes sin necesidad de mezclar o utilizar mixins, proporcionando una forma más clara y manteniente de manejar la lógica compartida.
2. **Encapsulación**: Ayudan a encapsular la lógica en funciones individuales, lo que mejora la modularidad y la organización del código.
3. **Reactividad**: Utilizan el sistema reactivo de Vue 3, permitiendo manejar estados reactivos y efectos secundarios de manera efectiva.

**Ejemplo de documentación de vue.**
```ts
// mouse.js
import { ref, onMounted, onUnmounted } from 'vue'

// by convention, composable function names start with "use"
export function useMouse() {
  // state encapsulated and managed by the composable
  const x = ref(0)
  const y = ref(0)

  // a composable can update its managed state over time.
  function update(event) {
    x.value = event.pageX
    y.value = event.pageY
  }

  // a composable can also hook into its owner component's
  // lifecycle to setup and teardown side effects.
  onMounted(() => window.addEventListener('mousemove', update))
  onUnmounted(() => window.removeEventListener('mousemove', update))

  // expose managed state as return value
  return { x, y }
}
```

```vue
<script setup>
import { useMouse } from './mouse.js'

const { x, y } = useMouse()
</script>

<template>Mouse position is at: {{ x }}, {{ y }}</template>
```

**Ejemplo de la App**
```ts
import { computed, ref, type Ref } from 'vue';

interface IuseCounter {
	counter : Ref<number>;
	squareCounter : Ref<number>;
}

export const useCounter = (value : number) : IuseCounter => {

	const counter = ref(value);
	const squareCounter = computed(() => counter.value * counter.value);
	
	return { counter, squareCounter };

};
```

