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
Los SFC permiten definir un componente en un solo archivo, generalmente con la extensión `.vue`. Estos archivos agrupan el código **HTML, CSS y JavaScript** necesarios para el componente en una estructura organizada y modular.

**Template (`<template>`)**: Aquí se define la estructura HTML del componente. Esta sección describe cómo se verá el componente en la interfaz de usuario.

**Script (`<script>`)**: En esta sección se escribe el código JavaScript que controla la lógica del componente. Aquí es donde se manejan los datos, métodos y ciclo de vida del componente.
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
			<button>+1</button>
			<button>-1</button>
		</div>
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

