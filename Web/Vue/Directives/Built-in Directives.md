## v-text
Lo que hace **`v-text`** es actualizar el texto de un elemento, es la forma larga de parte de un atributo de hacer el **mustache interpolation**.

```js
const { createApp, ref } = Vue;
const app = createApp({
	setup() {
		const msg = ref("estamos en vue")
		return { msg }
	}
});

app.mount('#app');
```

```html
<span v-text="msg"></span>
<span>{{msg}}</span>
```

El resultado seria **Estamos en Vue**
## v-html
Sirve para renderizar **HTML** proveniente del código. Esta practica como tal no es recomendada ya que puede ser sujeto de ataques **`XSS attacks`**
```js
const { createApp, ref } = Vue;
const app = createApp({
	setup() {
		const html_content = ref("<h1>Estamos en vue</h1>")
		return { html_content }
	}
});

app.mount('#app');
```

```html
<h1 v-html="html_content"></h1>
```

El resultado seria **Estamos en Vue** pero atravez de html del código.

## v-show
Lo que hace este atributo de Vue es aplicar un **`display : none`** a la etiqueta. por lo que **`v-if ≠ v-show`** ya que uno desaparece el elemento HTML y el otro solo lo oculta, este funciona atravez de un operador **booleano**.

```js
const { createApp, ref } = Vue;
const app = createApp({
	setup() {
		const msg = ref("Noctulo")
		return { msg }
	}
});
app.mount('#app');
```

```html
<span v-show="false">{{msg}}</span>
```

Así aparece en el HTML
```html
<h3 style="display: none;">Noctulo</h3>
```

## v-if
**`v-if`** no es mas que un simple condicional dentro de HTML, también funciona con operadores booleanos.

Es importante saber que este atributo hace una **destrucción y reconstrucción** del mismo para cambiar su valor, por lo que si hay procesos muy grandes y de alta memoria no usar abusivamente.

Y por ultimo no es recomendable usar **`v-if`** y **`v-for`** juntos en un mismo elemento ya que 
cuando existen en el mismo nodo, **`v-if`** tiene una prioridad mayor que **`v-for.`** Eso significa que la condición **`v-if`** no tendrá acceso a variables del alcance de **`v-for`**

**El mal ejemplo del uso del v-if**

```html
<ul>
  <li
    v-for="user in users"
    v-if="user.isActive"
    :key="user.id"
  >
    {{ user.name }}
  </li>
</ul>
```

**El buen ejemplo del v-if**

```html
<ul>
  <template v-for="user in users" :key="user.id">
    <li v-if="user.isActive">
      {{ user.name }}
    </li>
  </template>
</ul>
```


## v-else y v-else-if
Es el siguiente al **`v-if`** y se comporta exactamente igual solo que como resultado si no ocurre el **`if`**, ademas se puede encadenar con **`v-else-if`**

```html
<div v-if="type === 'A'">
  A
</div>
<div v-else-if="type === 'B'">
  B
</div>
<div v-else-if="type === 'C'">
  C
</div>
<div v-else>
  Not A/B/C
</div>
```

## v-for
El bucle **`v-for`** es para poder iterar muchos elementos dentro del html.

```js
const items = ref([...]) // items list
```

#### Forma común.
```html
<div v-for="item in items">
  {{ item.text }}
</div>
```

#### Forma destructorada
```html
<div v-for="({name, value} in items)">
  {{ item.name }} {{ item.value }}
</div>
```

#### Uso del key
El uso del **`key`** sirve para distinguir elementos únicos del array y mejora la optimazacion del mismo.

```html
<div v-for="item in items" :key="item.id">
  {{ item.text }}
</div>
```


## v-on
Simplemente lo que hace es adjuntar elementos de JS, este tiene un shorthand **`@`** y ademas tiene **`modifiers`**
### Modifiers
- `.stop` - call `event.stopPropagation()`.
- `.prevent` - call `event.preventDefault()`.
- `.capture` - add event listener in capture mode.
- `.self` - only trigger handler if event was dispatched from this element.
- `.{keyAlias}` - only trigger handler on certain keys.
- `.once` - trigger handler at most once.
- `.left` - only trigger handler for left button mouse events.
- `.right` - only trigger handler for right button mouse events.
- `.middle` - only trigger handler for middle button mouse events.
- `.passive` - attaches a DOM event with `{ passive: true }`.

```html
<!-- method handler -->
<button v-on:click="doThis"></button>
<!-- dynamic event -->
<button v-on:[event]="doThis"></button>
<!-- inline statement -->
<button v-on:click="doThat('hello', $event)"></button>
<!-- shorthand -->
<button @click="doThis"></button>
<!-- shorthand dynamic event -->
<button @[event]="doThis"></button>
<!-- stop propagation -->
<button @click.stop="doThis"></button>
<!-- prevent default -->
<button @click.prevent="doThis"></button>
<!-- prevent default without expression -->
<form @submit.prevent></form>
<!-- chain modifiers -->
<button @click.stop.prevent="doThis"></button>
<!-- key modifier using keyAlias -->
<input @keyup.enter="onEnter" />
<!-- the click event will be triggered at most once -->
<button v-on:click.once="doThis"></button>
<!-- object syntax -->
<button v-on="{ mousedown: doThis, mouseup: doThat }"></button>
```

## v-bind
La forma más común de usar **`v-bind`** es para enlazar atributos de HTML con datos del componente. Por ejemplo, si tienes un componente Vue con un dato llamado **`url`**, puedes enlazar este dato con el atributo **`href`** de un enlace **(`<a>`)**

```html
<template>
  <a v-bind="atributos">Ir a la página</a>
</template>

<script>
import { reactive } from 'vue';

export default {
  setup() {
    const atributos = reactive({
      href: 'https://www.ejemplo.com',
      target: '_blank',
      rel: 'noopener'
    });
    return { atributos };
  }
}
</script>
```

También **`v-bind`** tiene un short-hand cual seria **`:`**
```vue
<MyComponent :prop="someThing" />
```

## v-model
El **`v-model`** es usado para crear un **to way data binding** osea un enlazado  de dos lugares.
En palabras mas simples *"Si los inputs cambian de un lado también quiero que cambien del otro."*

```js
const name_user = ref("")
const users = ref([
{name: 'Alice', email: 'alice@example.com' },
{name: 'Bob', email: 'bob@example.com' },
{name: 'Charlie', email: 'charlie@example.com' },
{name: 'Dana', email: 'dana@example.com' },
{name: 'Eve', email: 'eve@example.com' }]);

const addUser = () => {
	users.value.push({name: name_user.value, email: `${ name_user.value.toLowerCase() }@example.com`})
name_user.value = ""

}
```

```html
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Build in</title>
</head>
	<body>
		<div id="app">
			<ul>
				<li v-for="{name, email} in users">
				{{ name }} {{ email }}
				</li>
			</ul>
			<input @keypress.enter="addUser" v-model="name_user" type="text">
		</div>
	</body>
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
<script src="app.js"></script>
</html>
```


## v-slots
**`v-slot`** es una directiva en Vue que se utiliza para definir y utilizar "slots" (espacios reservados) en componentes, lo que permite una mayor flexibilidad y re utilización del código. Los slots son áreas de un componente donde se puede insertar contenido dinámico, permitiendo que los componentes sean más versátiles y re utilizables.

*Continuar junto con Fernando...*


## v-is
La directiva **`v-is`** se utiliza para cambiar dinámicamente el componente que se renderiza en función de una condición. 

Esto es útil cuando se desea cambiar el componente que se renderiza en función de una condición, **como un estado o una propiedad.**

En el ejemplo que has proporcionado, `:is="selectedIcon"` le dice a Vue que renderice el componente que se asigna a `selectedIcon`. El valor de `selectedIcon` se determina en función del prop `iconName` que se pasa al componente