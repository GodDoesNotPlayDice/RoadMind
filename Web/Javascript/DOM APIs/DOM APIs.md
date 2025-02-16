**DOM APIs** significan **Interfaces de Programación de Aplicaciones del Modelo de Objetos del Documento** (Document Object Model, en inglés). Son un conjunto de herramientas que permiten a JavaScript interactuar con los elementos de una página web



## ¿Que es el DOM?
Es una representación en forma de **árbol** de todos los elementos HTML de una página (etiquetas, textos, atributos, etc.).

Actúa como un "puente" entre el código HTML y JavaScript, permitiendo modificar dinámicamente la estructura, contenido y estilos de la página. [Mas acerca del DOM](https://developer.mozilla.org/en-US/docs/Web/API/Document_Object_Model)
### Estructura del DOM
El DOM esta estructurado por [[Estructura del DOM]] cuales tienen **atributos, textos y comentarios**, ademas estos nodos se relacionan entre **padres, hijos y hermanos**

## ¿Que son las APIs en este contexto?
**APIs** (Application Programming Interfaces) son funciones y métodos predefinidos que los navegadores ofrecen para realizar acciones específicas.

Las **DOM APIs** son aquellas diseñadas específicamente para manipular el DOM. Por ejemplo:
- Seleccionar elementos (`querySelector`, `getElementById`).    
- Cambiar contenido (`textContent`, `innerHTML`).
- Modificar estilos (`style`, `classList`).
- Gestionar eventos (`addEventListener`).

**Ejemplo**
```js
// DOM API para seleccionar un elemento
const titulo = document.getElementById("miTitulo");

// DOM API para cambiar su contenido
titulo.textContent = "¡Hola Mundo!";

// DOM API para añadir un evento
titulo.addEventListener("click", () => {
    alert("Hiciste clic en el título");
});
```

## Cual es la diferencia de otras Web APIs?
Las **DOM APIs** están enfocadas en manipular **HTML/CSS**.

Otras Web APIs (como `localStorage`, `Geolocation`, o `fetch`) sirven para funcionalidades externas (almacenamiento, ubicación, conexiones a servidores).

## ¿Por qué son importantes?
Permiten crear páginas **dinámicas** (como actualizar contenido sin recargar la página).

Son esenciales para construir aplicaciones web interactivas (ej: redes sociales, juegos, formularios inteligentes).

## Ejemplos de uso de DOM APIs

### Seleccionar elementos
```js
// Por ID
const titulo = document.getElementById("miTitulo");

// Por selector CSS (primer elemento que coincida)
const parrafo = document.querySelector(".texto");

// Por selector CSS (todos los elementos)
const botones = document.querySelectorAll(".btn");
```

### Modificar contenido
```js
// Cambiar texto
titulo.textContent = "¡Nuevo título!";

// Cambiar HTML interno
parrafo.innerHTML = "<strong>Texto</strong> modificado";

// Cambiar atributos
const imagen = document.querySelector("img");
imagen.setAttribute("src", "nueva-imagen.jpg");
```

### Manipular estilos CSS
```js
// Estilo directo
titulo.style.color = "blue";
titulo.style.backgroundColor = "#f0f0f0";

// Clases CSS
botones.forEach(boton => {
    boton.classList.add("activo"); // Añadir clase
    boton.classList.remove("inactivo"); // Quitar clase
});
```

### Crear y eliminar elementos
```js
// Crear nuevo elemento
const nuevoParrafo = document.createElement("p");
nuevoParrafo.textContent = "Soy un párrafo nuevo";

// Añadir al final del body
document.body.appendChild(nuevoParrafo);

// Eliminar elemento
const elementoAEliminar = document.querySelector(".viejo");
elementoAEliminar.remove();
```

### Eventos
```js
// Click en un botón
const boton = document.querySelector("#miBoton");
boton.addEventListener("click", function() {
    console.log("¡Botón clickeado!");
});

// Formulario (evitar recarga de página)
const formulario = document.querySelector("form");
formulario.addEventListener("submit", function(event) {
    event.preventDefault(); // Detiene el comportamiento por defecto
    console.log("Formulario enviado");
});
```
