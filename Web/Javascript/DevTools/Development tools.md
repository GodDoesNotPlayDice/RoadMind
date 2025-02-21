## Using Browser DevTools
Las DevTools (como las de Chrome, Firefox o Edge) son herramientas integradas en los navegadores para inspeccionar, depurar y optimizar aplicaciones web. En JavaScript, permiten:

- **Acceder a la consola**: Ver errores, advertencias y logs con `console.log()`.
- **Inspeccionar elementos**: Modificar el DOM y estilos en tiempo real.
- **Analizar red**: Ver solicitudes HTTP y tiempos de carga.

## Debugging Issues
Es el proceso de identificar y corregir errores en el código. Ejemplos:
- **Breakpoints**: Pausar la ejecución en líneas específicas (en la pestaña **Sources**).
- **Call Stack**: Rastrear la secuencia de llamadas de funciones.
- **Watch Expressions**: Monitorear variables durante la ejecución.

**Ejemplo practico**
```js
function calcularSuma(a, b) {
    debugger; // Punto de interrupción manual
    return a + b;
}
console.log(calcularSuma(2, "3")); // Error: concatena en vez de sumar
```

## Debugging Memory Leaks
Una **fuga de memoria** ocurre cuando el programa no libera memoria innecesaria. Causas comunes en JavaScript: [[Memory Managment]]

- **Variables globales no liberadas**.
- **Event listeners olvidados**.
- **Referencias a elementos del DOM eliminados**.

### Herramientas
- **Memory Snapshot** (pestaña **Memory**): Compara instantáneas para detectar objetos no recolectados.
- **Performance Monitor**: Observa el uso de memoria en tiempo real.

## Debugging Performance
Optimizar el rendimiento del código para evitar lentitud. Herramientas clave:
- **Performance Tab**: Graba la ejecución para identificar cuellos de botella.
- **Lighthouse**: Genera reportes de rendimiento, accesibilidad y SEO.

### Problemas comunes
- **Funciones lentas**: Bucles pesados o operaciones síncronas bloqueantes.
- **Repintado excesivo del DOM** (reflows/repaints). [[Optimización del DOM]]. 

## Ejemplo de optimización

```js
// Evitar repintados múltiples
const lista = document.getElementById("lista");
// MAL: Modificar el DOM en cada iteración
for (let i = 0; i < 1000; i++) {
    lista.innerHTML += `<li>${i}</li>`;
}

// BIEN: Usar un fragmento para actualizar una sola vez
const fragment = document.createDocumentFragment();
for (let i = 0; i < 1000; i++) {
    const li = document.createElement("li");
    li.textContent = i;
    fragment.appendChild(li);
}
lista.appendChild(fragment);
```

