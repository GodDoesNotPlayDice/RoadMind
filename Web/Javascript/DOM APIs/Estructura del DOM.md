El DOM (Document Object Model) representa una página web como un **árbol de nodos**. Cada elemento, atributo, texto o comentario en el HTML es un **nodo** en este árbol. Esta estructura jerárquica permite navegar y manipular la página de manera organizada.

[Lista de Nodos y sus métodos](https://developer.mozilla.org/en-US/docs/Web/API/Node)

## Tipos de nodos
| Tipo de nodo          | Valor | Descripción                                    |
| --------------------- | ----- | ---------------------------------------------- |
| `Node.ELEMENT_NODE`   | 1     | Representa un elemento HTML (ej: `<div>`).     |
| `Node.ATTRIBUTE_NODE` | 2     | Representa un atributo (ej: `class="..."`).    |
| `Node.TEXT_NODE`      | 3     | Representa texto dentro de un elemento.        |
| `Node.COMMENT_NODE`   | 8     | Representa un comentario (ej: `<!-- ... -->`). |
| `Node.DOCUMENT_NODE`  | 9     | Representa el documento completo (`document`). |
Puedes verificar el tipo de un nodo usando la propiedad `nodeType`:

```js
const elemento = document.querySelector("div");
console.log(elemento.nodeType); // 1 (ELEMENT_NODE)
```

## Propiedades y métodos de los nodos
Los nodos tienen propiedades y métodos que te permiten navegar y manipular el DOM.

### Propiedades clave:
- `nodeName`: Devuelve el nombre del nodo (ej: `DIV`, `P`, `#text`).
- `nodeValue`: Devuelve el valor del nodo (útil para nodos de texto o comentarios).
- `childNodes`: Devuelve una lista de nodos hijos.
- `parentNode`: Devuelve el nodo padre.
- `nextSibling` y `previousSibling`: Devuelven los nodos hermanos.
- `firstChild` y `lastChild`: Devuelven el primer y último nodo hijo.

#### Relaciones entre nodos
Los nodos en el DOM están relacionados entre sí de manera jerárquica. Estas relaciones se describen con términos familiares como **padres**, **hijos** y **hermanos**.

##### Nodo padre
Es el nodo que **contiene** a otro nodo.
`<div>` es el nodo padre de `<p>`.

```js
<div>
    <p>Hola</p>
</div>
```

##### Nodo Hijos (`childNodes`)
Son los nodos **contenidos** dentro de otro nodo.
Los dos `<p>` son nodos hijos de `<div>`.

```js
<div>
    <p>Hola</p>
    <p>Mundo</p>
</div>
```

##### Nodos hermanos (`sibling nodes`)
Son nodos que **comparten el mismo padre**.
Los dos `<p>` son nodos hermanos.

```js
<div>
    <p>Hola</p>
    <p>Mundo</p>
</div>
```

##### Primer y último hijo (`firstChild`, `lastChild`)
`firstChild`: El primer nodo hijo.
`lastChild`: El último nodo hijo.

- `firstChild` es el primer `<p>` ("Hola").
- `lastChild` es el segundo `<p>` ("Mundo").

```js
<div>
    <p>Hola</p>
    <p>Mundo</p>
</div>
```

##### Hermano anterior y siguiente (`previousSibling`, `nextSibling`)
`previousSibling`: El nodo hermano anterior.
`nextSibling`: El nodo hermano siguiente.

- `previousSibling` es el primer `<p>` ("Hola").
- `nextSibling` es `null` (no hay hermano siguiente).

```js
<div>
    <p>Hola</p>
    <p>Mundo</p>
</div>
```

##### Explorar las relaciones en JS

```js
const contenedor = document.getElementById("contenedor");

// Nodo padre
console.log(contenedor.parentNode); // <body>

// Nodos hijos
console.log(contenedor.childNodes); // [comentario, <p>]

// Primer y último hijo
console.log(contenedor.firstChild); // <!-- Comentario -->
console.log(contenedor.lastChild); // <p>

// Hermanos
const parrafo = document.querySelector("p");
console.log(parrafo.previousSibling); // <!-- Comentario -->
console.log(parrafo.nextSibling); // null
```
## Ejemplos prácticos

### Navegar entre nodos
```js
 const div = document.querySelector("div");

// Nodo padre
console.log(div.parentNode);

// Primer hijo
console.log(div.firstChild);

// Siguiente hermano
console.log(div.nextSibling);
```

### Crear y añadir nodos
```js
// Crear un nuevo nodo de texto
const texto = document.createTextNode("Hola, soy un nodo de texto");

// Crear un nuevo elemento
const parrafo = document.createElement("p");
parrafo.appendChild(texto); // Añadir el texto al párrafo

// Añadir el párrafo al body
document.body.appendChild(parrafo);
```

### Clonar un nodo
```js
const original = document.querySelector(".original");
const clonado = original.cloneNode(true); // true para clonar con hijos
document.body.appendChild(clonado);
```

### Eliminar un nodo
```js
const elementoAEliminar = document.querySelector(".eliminar");
elementoAEliminar.parentNode.removeChild(elementoAEliminar);
```

### Nodos de texto
Los nodos de texto (`Node.TEXT_NODE`) representan el contenido textual dentro de los elementos. Por ejemplo:

```js
<p>Hola, <strong>mundo</strong></p>
```

- El texto `"Hola, "` es un nodo de texto.
- El elemento `<strong>` es un nodo de tipo `ELEMENT_NODE`.
- El texto `"mundo"` dentro de `<strong>` es otro nodo de texto.

es posible acceder a ellos:

```js
const parrafo = document.querySelector("p");
console.log(parrafo.childNodes); // [texto "Hola, ", elemento <strong>]
```

### Nodos y espacios en blanco
Los navegadores crean nodos de texto para los espacios en blanco y saltos de línea en el HTML.

Esto puede afectar cómo navegas por el DOM. Por ejemplo:

```js
<div>
  <p>Hola</p>
</div>
```

El `div` tiene 3 nodos hijos: un nodo de texto (espacio), un nodo `<p>`, y otro nodo de texto (espacio).

### Document Fragment
Es un tipo especial de nodo que actúa como un contenedor temporal para otros nodos.
Útil para hacer múltiples cambios al DOM sin afectar el rendimiento.

```js
const fragment = document.createDocumentFragment();

for (let i = 0; i < 10; i++) {
    const div = document.createElement("div");
    div.textContent = `Elemento ${i}`;
    fragment.appendChild(div);
}

document.body.appendChild(fragment); // Añade todos los nodos de una vez
```

