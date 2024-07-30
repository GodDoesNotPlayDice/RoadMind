
Hemos aprendido que los componentes pueden aceptar `props`, que pueden ser valores de JavaScript de cualquier tipo. Pero ¿qué pasa con el contenido de la plantilla? En algunos casos, es posible que deseemos pasar un fragmento de plantilla a un componente secundario y dejar que el componente secundario represente el fragmento dentro de su propia plantilla.

1) [Single slot](#Single-slot)
2) [Multi Slot](#Multiple-Slot)

![[Pasted image 20240730150110.png]]

### Single-Slot

El primer ejemplo es simple con un **fallback**, y el componente con un **slot**, donde si no es recibido el texto en el slop es puesto un fallback en el **`slot`**.

**`App.vue`**
```vue
<script setup>
import SubmitButton from './SubmitButton.vue'
</script>

<template>
	<!-- use fallback text -->
	<SubmitButton />
	<!-- provide custom text -->
	<SubmitButton>Save</SubmitButton>
</template>


<script setup>
	import ChildComponent from './ChildComponent.vue';
</script>
```

**`SubmitButton.vue`**
```vue
<template>
	<button type="submit">
		<slot>
			Submit <!-- fallback content -->
		</slot>
	</button>
</template>
```


### Multiple-Slot
El **multi slot** consiste en tener el componente y dentro de el, mas de un **template**, para poder nombrarlo con un atributo `#name` cual es identificado por el slot con `name`.

```vue
<template>
	<ChildComponent>
	
	<template #header>
		<h1>This is the header</h1>
	</template>
	
	<template #default>
		<p>This is the main content</p>
	</template>
	
	
	<template #footer>
		<p>This is the footer</p>
	</template>
	
	</ChildComponent>
</template>

  
<script setup>

import ChildComponent from './ChildComponent.vue';

</script>
```

```vue
<template>
  <div>
    <header>
      <slot name="header">Default Header Content</slot>
    </header>
    <main>
      <slot>Default Main Content</slot>
    </main>
    <footer>
      <slot name="footer">Default Footer Content</slot>
    </footer>
  </div>
</template>

<script setup>
</script>

```