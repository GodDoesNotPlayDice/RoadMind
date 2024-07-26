## Multi-word
Esta regla requiere que los nombres de los componentes tengan siempre varias palabras, excepto los componentes **raíz** ⇒ **App.vue** de la aplicación y los componentes integrados proporcionados por Vue, como `transition` o `component` .
**Esto evita conflictos con elementos HTML existentes y futuros**, ya que todos los elementos HTML son palabras únicas.

```js
/* ✓ GOOD */
Vue.component('todo-item', {
// ...
})

/* ✗ BAD */
Vue.component('Todo', {
// ...
})
```
