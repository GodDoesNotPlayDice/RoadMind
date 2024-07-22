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

**Forma comun.**
```html
<div v-for="item in items">
  {{ item.text }}
</div>
```

**Forma destructorada**  
```html
<div v-for="({name, value} in items)">
  {{ item.name }} {{ item.value }}
</div>
```



