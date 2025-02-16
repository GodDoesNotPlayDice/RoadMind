JavaScript son una parte fundamental de la interacción con el usuario en una página web. Permiten ejecutar código en respuesta a acciones del usuario, como hacer clic en un botón, mover el mouse, presionar una tecla, etc.


## ¿Qué es un Evento?
Un evento es una acción o ocurrencia que sucede en el navegador, como:
- Hacer clic en un elemento (`click`).
- Mover el mouse sobre un elemento (`mouseover`).
- Presionar una tecla (`keydown`).
- Cargar una página (`load`).
- Enviar un formulario (`submit`).

## Manejadores de Eventos
Un manejador de eventos (event handler) es una función que se ejecuta cuando ocurre un evento. Hay varias formas de asignar manejadores de eventos:

### Manejador en línea (en HTML)
Puedes asignar un evento directamente en el HTML usando atributos como `onclick`, `onmouseover`, etc.

```html
<button onclick="alert('Hiciste clic!')">Haz clic</button>
```

### Manejador en Javascript
Es más común y recomendable asignar los eventos directamente en el JavaScript para separar la lógica del HTML.

```js
<button id="miBoton">Haz clic</button>

<script>
  document.getElementById('miBoton').onclick = function() {
    alert('Hiciste clic!');
  };
</script>
```

### Usar `addEventListener`
Este método es más flexible y permite agregar múltiples manejadores al mismo evento.

```html
<button id="miBoton">Haz clic</button>

<script>
  document.getElementById('miBoton').addEventListener('click', function() {
    alert('Hiciste clic!');
  });
</script>
```


## Tipos de Eventos Comunes
Aquí tienes algunos de los eventos más utilizados:

### Eventos del Mouse:
- `click`: Cuando se hace clic en un elemento.
- `dblclick`: Cuando se hace doble clic en un elemento.
- `mouseover`: Cuando el mouse pasa sobre un elemento.
- `mouseout`: Cuando el mouse sale de un elemento.
- `mousemove`: Cuando el mouse se mueve sobre un elemento

### Eventos del Teclado:
- `keydown`: Cuando se presiona una tecla.
- `keyup`: Cuando se suelta una tecla.
- `keypress`: Cuando se presiona y suelta una tecla (obsoleto, usa `keydown` o `keyup`).

### Eventos del formulario:
- `submit`: Cuando se envía un formulario.
- `change`: Cuando cambia el valor de un input, select o textarea.
- `focus`: Cuando un elemento recibe el foco.
- `blur`: Cuando un elemento pierde el foco.

### Eventos de la Ventana
- `load`: Cuando la página ha terminado de cargar.
- `resize`: Cuando se redimensiona la ventana.
- `scroll`: Cuando se desplaza la página.

## Objeto Event
Cuando ocurre un evento, el navegador crea un objeto `Event` que contiene información sobre el evento. Este objeto se pasa automáticamente a la función manejadora.

```js
document.getElementById('miBoton').addEventListener('click', function(event) {
  console.log(event); // Muestra el objeto Event
  console.log(event.type); // Tipo de evento, en este caso "click"
  console.log(event.target); // Elemento que desencadenó el evento
});
```

## Propagación de eventos (Bubbling y Capturing)
Los eventos en JavaScript se propagan en dos fases:
- **Capturing (Fase de Captura):** El evento desciende desde el elemento raíz hasta el elemento objetivo.
- **Bubbling (Fase de Burbuja):** El evento asciende desde el elemento objetivo hasta el elemento raíz.

Puedes controlar la fase en la que se ejecuta el manejador usando el tercer parámetro de `addEventListener`:

```js
document.getElementById('miBoton').addEventListener('click', function() {
  alert('Fase de burbuja');
}, false); // false (por defecto) para la fase de burbuja, true para la fase de captura
```

### Explicación con peras y manzanas
Imagina que tienes una caja de frutas **(un contenedor)** que contiene una manzana y una pera. Cuando haces clic en la manzana o en la pera, queremos ver cómo se propaga el evento desde el contenedor **(la caja de frutas)** hasta la fruta específica **(fase de captura)** y luego de regreso desde la fruta hasta el contenedor **(fase de burbuja).**

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Propagación de Eventos - Peras y Manzanas</title>
  <style>
    /* Estilos para la caja de frutas y las frutas */
    #cajaDeFrutas {
      border: 2px solid #333;
      padding: 20px;
      background-color: #f9f9f9;
      width: 300px;
      margin: 20px auto;
      text-align: center;
    }

    #manzana, #pera {
      padding: 10px;
      margin: 10px;
      cursor: pointer;
    }

    #manzana {
      background-color: #ffcccc; /* Color rojo claro para la manzana */
    }

    #pera {
      background-color: #ccffcc; /* Color verde claro para la pera */
    }
  </style>
</head>
<body>
  <div id="cajaDeFrutas">
    <div id="manzana">Manzana 🍎</div>
    <div id="pera">Pera 🍐</div>
  </div>

  <script>
    // Seleccionamos la caja de frutas y las frutas
    const cajaDeFrutas = document.getElementById('cajaDeFrutas');
    const manzana = document.getElementById('manzana');
    const pera = document.getElementById('pera');

    // Manejadores de eventos para la fase de captura (tercer parámetro: true)
    cajaDeFrutas.addEventListener('click', function(event) {
      console.log('Captura: Caja de frutas');
    }, true);

    manzana.addEventListener('click', function(event) {
      console.log('Captura: Manzana 🍎');
    }, true);

    pera.addEventListener('click', function(event) {
      console.log('Captura: Pera 🍐');
    }, true);

    // Manejadores de eventos para la fase de burbuja (tercer parámetro: false o omitido)
    cajaDeFrutas.addEventListener('click', function(event) {
      console.log('Burbuja: Caja de frutas');
    }, false);

    manzana.addEventListener('click', function(event) {
      console.log('Burbuja: Manzana 🍎');
    }, false);

    pera.addEventListener('click', function(event) {
      console.log('Burbuja: Pera 🍐');
    }, false);
  </script>
</body>
</html>
```
#### Explicación
- **Fase de Captura:**
    - El evento comienza en el elemento raíz (`#cajaDeFrutas`) y desciende hasta el elemento objetivo (la fruta en la que hiciste clic).
    - Por eso los mensajes de "Captura" aparecen primero.
1. **Fase de Burbuja:**
    - Después de llegar al elemento objetivo, el evento asciende de nuevo hasta el elemento raíz (`#cajaDeFrutas`).
    - Por eso los mensajes de "Burbuja" aparecen después.
#### ¿Como funciona?
##### Estructura HTML:
- Tenemos un contenedor (`#cajaDeFrutas`) que contiene dos elementos: una manzana (`#manzana`) y una pera (`#pera`).
- Cada fruta tiene un texto y un emoji para identificarla visualmente.
##### Estilos CSS
- La caja de frutas tiene un borde y un fondo claro.
- La manzana tiene un fondo rojo claro, y la pera tiene un fondo verde claro.
- Ambas frutas tienen un cursor de tipo "pointer" para indicar que son clickeables.
##### Javascript
- Se agregan manejadores de eventos para la **fase de captura** (usando `true` como tercer parámetro en `addEventListener`).
- Se agregan manejadores de eventos para la **fase de burbuja** (usando `false` o omitiendo el tercer parámetro en `addEventListener`).
- Cada manejador imprime un mensaje en la consola indicando la fase y el elemento en el que se ejecutó.
!
#### ¿Resultado del click?

**Manzana**
```js
Captura: Caja de frutas
Captura: Manzana 🍎
Burbuja: Manzana 🍎
Burbuja: Caja de frutas
```

**Pera**
```js
Captura: Caja de frutas
Captura: Pera 🍐
Burbuja: Pera 🍐
Burbuja: Caja de frutas
```

## Detener la propagación y Prevenir
- **`event.stopPropagation()`:** Detiene la propagación del evento.
- **`event.preventDefault()`:** Previene el comportamiento por defecto del evento (por ejemplo, evitar que un formulario se envíe).

```js
document.getElementById('miBoton').addEventListener('click', function(event) {
  event.stopPropagation(); // Detiene la propagación
  event.preventDefault(); // Previene el comportamiento por defecto
});
```

## Delegación de eventos
La delegación de eventos es una técnica que consiste en asignar un manejador de eventos a un elemento padre para manejar eventos de sus elementos hijos. Esto es útil cuando tienes muchos elementos dinámicos.

```html
<ul id="miLista">
  <li>Item 1</li>
  <li>Item 2</li>
  <li>Item 3</li>
</ul>

<script>
  document.getElementById('miLista').addEventListener('click', function(event) {
    if (event.target.tagName === 'LI') {
      alert('Hiciste clic en: ' + event.target.textContent);
    }
  });
</script>
```

## Eventos personalizados
Puedes crear y disparar tus propios eventos personalizados.

```js
// Crear un evento personalizado
let eventoPersonalizado = new CustomEvent('miEvento', {
  detail: { mensaje: 'Este es un evento personalizado' }
});

// Escuchar el evento
document.addEventListener('miEvento', function(event) {
  console.log(event.detail.mensaje);
});

// Disparar el evento
document.dispatchEvent(eventoPersonalizado);
```

## Eliminar Manejadores de Eventos
Puedes eliminar un manejador de eventos usando `removeEventListener`.

```js
function manejarClic() {
  alert('Hiciste clic!');
}

document.getElementById('miBoton').addEventListener('click', manejarClic);

// Eliminar el manejador de eventos
document.getElementById('miBoton').removeEventListener('click', manejarClic);
```


## Ejemplo completo

```html
<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <title>Eventos en JavaScript</title>
</head>
<body>
  <button id="miBoton">Haz clic</button>
  <ul id="miLista">
    <li>Item 1</li>
    <li>Item 2</li>
    <li>Item 3</li>
  </ul>

  <script>
    // Manejador de eventos para el botón
    document.getElementById('miBoton').addEventListener('click', function(event) {
      alert('Hiciste clic en el botón!');
    });

    // Delegación de eventos para la lista
    document.getElementById('miLista').addEventListener('click', function(event) {
      if (event.target.tagName === 'LI') {
        alert('Hiciste clic en: ' + event.target.textContent);
      }
    });

    // Evento personalizado
    let eventoPersonalizado = new CustomEvent('miEvento', {
      detail: { mensaje: 'Este es un evento personalizado' }
    });

    document.addEventListener('miEvento', function(event) {
      console.log(event.detail.mensaje);
    });

    document.dispatchEvent(eventoPersonalizado);
  </script>
</body>
</html>
```

