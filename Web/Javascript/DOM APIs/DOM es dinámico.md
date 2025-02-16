Cualquier cambio que hagas con JavaScript se refleja **inmediatamente** en la página, el DOM no es estático: puedes **añadir**, **eliminar** o **modificar** elementos, atributos y contenido directamente desde JavaScript.

**Ejemplo**
```js
const div = document.createElement("div");
div.textContent = "¡Nuevo div!";
document.body.appendChild(div); // Aparece en la página al instante.
```

## Dinamismo y Eventos
Los eventos permiten que el DOM reaccione a las acciones del usuario, como clics, movimientos del mouse, o pulsaciones de teclas. Esto hace que la página sea interactiva.

Los eventos en JS [[Eventos]]

