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

**El mal ejemplo**
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

**El buen ejemplo**
```html
<ul>
  <li
    v-for="user in activeUsers"
    :key="user.id"
  >
    {{ user.name }}
  </li>
</ul>
```

```html
<ul>
  <template v-for="user in users" :key="user.id">
    <li v-if="user.isActive">
      {{ user.name }}
    </li>
  </template>
</ul>
```