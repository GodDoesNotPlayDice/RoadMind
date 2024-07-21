## Temario
Esta sección empezará a dejar las bases de todo lo que normalmente usaremos en el día a día creando aplicaciones con VueJS

1. CompositionAPI vs OptionsAPI
2. Hola Mundo en Vue
3. Vue mediante CDN
4. Propiedades reactivas con Ref

## Descripción de Vue
Según la pagina oficial es un framework progresivo, ya que cuando se inicia un proyecto puede adaptarse a otro proyecto ya iniciado y solo seccionarse en una parte, o usarse en toda la app.


## CompositionAPI vs OptionsAPI
Son dos tipos de sintaxis, donde la **CompositionAPI** es la manera nueva de escribir **Vue** y a su contraste **OptionsAPI** es la version vieja de escribir.


## Vue mediante CDN
Esto es una vaina loca, ya que cuando ocupamos Vue podemos hacer dos cosas muy buenas
1. Primera es seccionar **vue.js** en parte de proyectos ya creados con otro lenguaje.
2. Segunda hacer un proyecto full en **vue.js**.

La primera forma que es con **CDN** es un super poder del framework.

Podemos crear un HTML normal y insertar la CDN, la magia va en el app.js
```html
<!DOCTYPE html>

<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vue Js</title>
  </head>
  <body>
  
    <div id="app"></div>
    
  </body>
  <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
  <script src="/app.js"></script>
</html>
```

En app.js junto a la previa importación del script de Vue, podemos tomar el objeto de Vue y con esto crear una **app**. para hacerlo son dos simples pasos en la constante

tomar **createApp** cuyo es para crear la app y **ref** que sirve para referenciar el objeto en el ciclo de vida del estado de Vue, de esta forma al darle **ref** a un valor, Vue va saber o estar pendiente de ese objeto por lo que lo va a re-renderizar cuando haya un cambio.

Luego tenemos el **template** que es lo que va renderizar nuestra app.js, a esta le podemos pasar variables del ciclo de vida Vue, usando `{{ }}` para pasar las variables.

Al final usaremos **`app.mount(#app)`** para pasar la constante como **id** y poder incrustarlo en el HTML.
```js
const { createApp, ref } = Vue;
const app = createApp({
    template: `
        <div>
            <h1>{{ message }}</h1>
            <input v-model="message" />
        </div>
    `,
    setup() {
        const message = ref('Hello Vue 3!');
        return { message };
    }
});

app.mount('#app');
```

## Propiedades reactivas
Podemos hacer reactiva una propiedad a los cambios

Creamos un botón y con la propiedad **`v-on:click`** podemos asignar una función referenciada para ejecutar código.
```html
    <div id="app">
        <h3>{{ message }}</h3>
        <button v-on:click="changeMessage" >Cambiar mensaje</button>
    </div>
```

Creamos la función normal de JavaScript **(`changeMessage`)** para ejecutarla con el atributo previo de Vue.
```js
const { createApp, ref } = Vue;
const app = createApp({
    setup() {
        const message = ref('Noctulo');
        
        const changeMessage = () => {
            message.value = 'Noctulo reactivo';
        }
        
        return { message, changeMessage };
    }
});
app.mount('#app');
```


### Bucle v-for
El bucle v-for es para poder iterar muchos elementos dentro del html.
#### Lista con quotes.
```js
const { createApp, ref } = Vue;
const app = createApp({
  setup() {
    const quotes = [
      {
        quote:
          "The night is darkest just before the dawn. And I promise you, the dawn is coming.",
        author: "Harvey Dent, The Dark Knight",
      },
      {
        quote: "I believe what doesn’t kill you simply makes you, stranger.",
        author: "The Joker, The Dark Knight",
      },
      {
        quote: "Your anger gives you great power. But if you let it, it will destroy you… As it almost did me",
        author: "Henri Ducard, Batman Begins",
      },
      {
        quote:"You either die a hero or live long enough to see yourself become the villain.",
        author: "Harvey Dent, The Dark Knight",
      },
      {
        quote: "If you’re good at something, never do it for free.",
        author: "The Joker, The Dark Knight",
      },
      {
        quote: "Yes, father. I shall become a bat.",
        author: "Bruce Wayne/Batman, Batman: Year One",
      },
    ];
    return { quotes }
  }, 
});

app.mount("#app");
```

Debemos hacer 
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    <div id="app">
        <ul>
            <li v-for="quote in quotes">
               {{ quote.author }}
            </li>
        </ul>
    </div>
</body>
<script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
<script src="/app.js"></script>
</html>
```

### v-if and v-show
#### v-if
**`v-if`** no es mas que un simple condicional dentro de HTML.
```html
<div id="app">
	<ul>
		<li v-for="({quote, author}, index) in quotes">
			<span>{{index + 1}} - {{quote}}</span>
			<blockquote v-if="showAuthor">{{ author }}</blockquote> <!-- true -->

		</li>
	</ul>
	<button @click="toggleAuthor()" >Toggle Author</button>
</div>
```

Caso del **toggle** reactivo de Vue, ocurre algo particular con Vue cuando hacemos una variable reactiva y esa es en el **valor** en Vue el valor se desenvuelve directamente en el HTML **`showAuthor`** ≠ **`showAuthor.value`**

#### v-show
Lo que hace este atributo de Vue es aplicar un **`display : none`** a la etiqueta. por lo que **`v-if ≠ v-show`** ya que uno desaparece el elemento HTML y el otro solo lo oculta.

```html
<div id="app">
	<ul>
		<li v-for="({quote, author}, index) in quotes">
			<span>{{index + 1}} - {{quote}}</span>
			<blockquote v-show="showAuthor">{{ author }}</blockquote> <!-- true / false -->

		</li>
	</ul>
	<button @click="toggleAuthor()" >Toggle Author</button>
</div>
```


#### Cuando usar?
Es sencillo, **`v-if`** lo que principalmente hace es re-renderizar un componente por lo que en un **toggle** el elemento se **rederiza** y se **desrenderiza** entonces esto en una tarea pesada puede consumir muchos recursos y ahí es cuando entra **`v-show`**  


### Agregar elementos a un Array y re-renderizarlo
Podemos lograr esto agregando la función **`ref()`** al array con objetos.
Es importante tomar el valor del array ya que como estamos trabajando en el código y no en HTML debemos usar **`value`** para tomar el array y usar sus métodos.

```js
const quotes_arr = [......];
const quotes = ref(quotes_arr);

const addQuote = () => {
	quotes.value.unshift/push({...})
}

```

### v-model
El **`v-model`** es usado para crear un **to way data binding** osea un enlazado  de dos lugares.
En palabras mas simples *"Si los inputs cambian de un lado también quiero que cambien del otro."*

