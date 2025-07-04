Además del conjunto predeterminado de directivas incluidas en el núcleo (como v-model o v-show), Vue también le permite registrar sus propias directivas personalizadas.

Las directivas personalizadas solo deben usarse cuando la funcionalidad deseada solo se puede lograr mediante manipulación directa de DOM.

Prefiera plantillas declarativas utilizando directivas integradas como v-bind cuando sea posible porque son más eficientes y fáciles de procesar en el servidor.


Existen dos formas de reutilización de código en Vue: 
- [[Web/Vue/Docs/Esencial/Components/Components]] : los **componentes** son los bloques de construcción principales
- [[Web/Vue/Docs/Esencial/Composables/Composables]] : los elementos **componibles** se centran en reutilizar la lógica con estado

Las directivas personalizadas, por otro lado, están destinadas principalmente a reutilizar la lógica que implica acceso DOM de bajo nivel en elementos simples.


Una **directiva personalizada** se define como un objeto que contiene **enlaces de ciclo de vida similares a los de un componente**. 

Los `Hooks` reciben el elemento al que está vinculada la directiva. 

**`Ejemplo`**
Suponiendo que no haya hecho clic en ninguna otra parte de la página, la entrada anterior debería tener enfoque automático.

Esta directiva es más útil que el atributo de enfoque automático porque no solo funciona al cargar la página, sino que también funciona cuando Vue inserta dinámicamente el elemento.
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


En `<script setup>`, cualquier variable camelCase que comience con el prefijo `v` se puede utilizar como directiva personalizada. En el ejemplo anterior, `vFocus` se puede utilizar en la plantilla como `v-focus`.

Si no se utiliza `<script setup>`, las directivas personalizadas se pueden registrar usando las directivas.

```ts
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

También es común registrar globalmente directivas personalizadas a nivel de aplicación.

```ts
const app = createApp({})

// make v-focus usable in all components
app.directive('focus', {
  /* ... */
})
```

## Directive Hooks
Un objeto de definición de directiva puede proporcionar varias funciones de enlace.

```js
const myDirective = {
  // called before bound element's attributes
  // or event listeners are applied
  created(el, binding, vnode) {
    // see below for details on arguments
  },
  // called right before the element is inserted into the DOM.
  beforeMount(el, binding, vnode) {},
  // called when the bound element's parent component
  // and all its children are mounted.
  mounted(el, binding, vnode) {},
  // called before the parent component is updated
  beforeUpdate(el, binding, vnode, prevVnode) {},
  // called after the parent component and
  // all of its children have updated
  updated(el, binding, vnode, prevVnode) {},
  // called before the parent component is unmounted
  beforeUnmount(el, binding, vnode) {},
  // called when the parent component is unmounted
  unmounted(el, binding, vnode) {}
}
```
### Hook Arguments
Los `hooks` directivos se pasan a estos argumentos.

**`el`**: el elemento al que está vinculada la directiva. Esto se puede utilizar para manipular directamente el DOM.

**`binding`**: Un objeto que contiene las siguientes propiedades.
- `value`: El valor pasado a la directiva. Por ejemplo, en `v-my-directive="1 + 1",` el valor sería `2`.
- `oldValue`:El valor anterior, sólo disponible en `beforeUpdate` y `updated`.Está disponible independientemente de si el valor ha cambiado o no.
- `arg`: El argumento pasó a la directiva, si la hubiera. Por ejemplo, en `v-my-directive:foo,` el argumento sería `"foo".`
- `modifiers`: Un objeto que contiene modificadores, si los hay. Por ejemplo en `v-my-directive.foo.bar`, el objeto modificadores sería `{ foo: true, bar: true }`.
- `instance`: La instancia del componente donde se utiliza la directiva.
- `dir`: el objeto de definición de directiva.

**`vnode`**: el VNode subyacente que representa el elemento vinculado.
**`prevVnode`**: el VNode que representa el elemento enlazado del renderizado anterior. Sólo disponible en el `beforeUpdate` y `updated` hooks.

```vue
<div v-example:foo.bar="baz">
```

El argumento `binding` sería un objeto con la forma de:

```ts{
  arg: 'foo',
  modifiers: { bar: true },
  value: /* value of `baz` */,
  oldValue: /* value of `baz` from previous update */
}
```

Al igual que las directivas integradas, los argumentos de las directivas personalizadas pueden ser dinámicos.

```vue
<div v-example:[arg]="value"></div>
```

Aquí el argumento de la directiva se actualizará reactivamente según la propiedad `arg` en el estado de nuestro componente.

### Shorts-hands

Es común que una directiva personalizada tenga el mismo comportamiento para `mounted` y `update`, sin necesidad de otros enlaces. En tales casos podemos definir la directiva como una función:

```vue
<div v-color="color"></div>
```

```ts
app.directive('color', (el, binding) => {
  // this will be called for both `mounted` and `updated`
  el.style.color = binding.value
})
```

### Object-Literals
Si su directiva necesita varios valores, también puede pasar un objeto literal de JavaScript. Recuerde, las directivas pueden tomar cualquier expresión JavaScript válida.
```vue
<div v-demo="{ color: 'white', text: 'hello!' }"></div>
```

```js
app.directive('demo', (el, binding) => {
  console.log(binding.value.color) // => "white"
  console.log(binding.value.text) // => "hello!"
})
```

