## Indice
1. **Iniciar un proyecto**: [[Start a project]] Iniciar un proyecto usando `tailwind`
2. Crear una **App**: [[Create App]] Crear una app usando **Vue** mediante **CDN** o **SFC**
3. **Componentes**: [[Web/Vue/Docs/Esencial/Components/Components]]
4. **Composables**: [[Web/Vue/Docs/Esencial/Composables/Composables]]
5. **Directivas**: [[Built-in Directives]] y [[Custom Directives]]

### Notas
- **Proyectos**:  [[Notas de Proyectos]]
- **Testing**: [[Testing]]

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

Al final usaremos **`app.mount(#app)`** para pasar la constante como **id** y poder incrustarlo en el HTML. [[Create App]]
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


