
- **Añadir, eliminar o modificar elementos HTML.**
- **Cambiar atributos** (como `class`, `id`, `src`, etc.).
- **Modificar el contenido** (texto, imágenes, etc.).
- **Cambiar estilos CSS** en tiempo real.

## ¿Por qué es importante?
La manipulación del DOM es esencial para crear páginas web **dinámicas e interactivas**. Algunos ejemplos comunes incluyen:
1) **Actualizar contenido sin recargar la página:** Como en aplicaciones de redes sociales o chats.
2) **Validar formularios en tiempo real:** Mostrar mensajes de error o éxito sin recargar.
3) **Crear animaciones y efectos:** Cambiar estilos o posiciones de elementos.
4) **Responder a acciones del usuario:** Como clics, movimientos del mouse o pulsaciones de teclas.

## Métodos importantes

### Selección de elementos
- **`document.getElementById(id)`**: Selecciona un elemento por su `id`.
- **`document.querySelector(selector)`**: Selecciona el primer elemento que coincide con el selector CSS.
- **`document.querySelectorAll(selector)`**: Selecciona todos los elementos que coinciden con el selector CSS (devuelve una NodeList).
- **`document.getElementsByClassName(clase)`**: Selecciona elementos por su clase (devuelve una HTMLCollection).
- **`document.getElementsByTagName(etiqueta)`**: Selecciona elementos por su etiqueta (devuelve una HTMLCollection).

### Modificación de contenido
- **`element.textContent`**: Obtiene o establece el texto de un elemento (ignora etiquetas HTML).
- **`element.innerHTML`**: Obtiene o establece el contenido HTML de un elemento.
- **`element.innerText`**: Obtiene o establece el texto visible (depende del CSS).

### Modificación de estilos
- **`element.style.prop`**: Modifica estilos en línea (por ejemplo, `element.style.color = "red"`).
- **`element.classList`**: Métodos para manipular clases CSS:
    - `add(clase)`: Añade una clase.
    - `remove(clase)`: Elimina una clase.
    - `toggle(clase)`: Alterna una clase.
    - `contains(clase)`: Verifica si tiene una clase.

### Creación de elementos
- **`document.createElement(tag)`**: Crea un nuevo elemento HTML.
- **`document.createTextNode(texto)`**: Crea un nodo de texto.

### Añadir elementos al DOM
- **`element.appendChild(nuevoElemento)`**: Añade un elemento como último hijo.
- **`element.insertBefore(nuevoElemento, referencia)`**: Inserta un elemento antes de otro.
- **`element.append(...nodos)`**: Añade nodos al final (más moderno que `appendChild`).
- **`element.prepend(...nodos)`**: Añade nodos al principio.

### Eliminación de elementos
- **`element.remove()`**: Elimina el elemento directamente.
- **`element.removeChild(elementoHijo)`**: Elimina un hijo específico.

### Clonación de elementos
- **`element.cloneNode(deep)`**: Clona un elemento. Si `deep` es `true`, clona también sus hijos.

### Manejo de eventos
- **`element.addEventListener(evento, callback)`**: Añade un evento a un elemento.
- **`element.removeEventListener(evento, callback)`**: Elimina un evento de un elemento.

### Navegación entre nodos
Hay una explicación mas clara de la navegación del DOM, [[Estructura del DOM]] 

- **`element.parentNode`**: Obtiene el nodo padre.
- **`element.childNodes`**: Obtiene todos los nodos hijos (incluyendo texto y comentarios).
- **`element.children`**: Obtiene solo los elementos hijos.
- **`element.nextElementSibling`**: Obtiene el siguiente hermano.
- **`element.previousElementSibling`**: Obtiene el hermano anterior.

### Manipulación de clases
- **`element.className`**: Obtiene o establece todas las clases de un elemento.
- **`element.classList`**: Métodos para manipular clases (ver sección 4).

### Manipulación de formularios
- **`formElement.value`**: Obtiene o establece el valor de un input.
- **`formElement.reset()`**: Reinicia un formulario.
- **`formElement.submit()`**: Envía un formulario.


## Ejemplo practico

```js
// Seleccionar un elemento
const div = document.querySelector("#miDiv");

// Modificar contenido
div.textContent = "Hola Mundo";
div.innerHTML = "<strong>Texto</strong> con formato";

// Añadir una clase
div.classList.add("destacado");

// Crear y añadir un nuevo elemento
const nuevoParrafo = document.createElement("p");
nuevoParrafo.textContent = "Este es un nuevo párrafo";
div.appendChild(nuevoParrafo);

// Eliminar un elemento
nuevoParrafo.remove();
```