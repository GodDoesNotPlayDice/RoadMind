React implementa un proceso de renderizado que se centra en la eficiencia y la claridad del código, aprovechando una serie de técnicas que optimizan la forma en que se actualiza la interfaz de usuario (UI).

# Enfoque declarativo
En lugar de interactuar directamente con el DOM (Document Object Model) para actualizar elementos de la página, React adopta un **enfoque declarativo**.

Esto significa que el desarrollador se concentra en describir **qué** se debe renderizar, es decir, define la estructura y apariencia de los componentes utilizando JSX / TSX.

En este paradigma, el componente es una función (o una clase) que, dados ciertos datos (props y state), devuelve un **árbol de elementos** que describe la UI deseada.

## Ventajas
**Simplicidad y claridad:** El código se vuelve más legible y predecible porque se declara el resultado final en lugar de imperar sobre cómo alcanzarlo.

**Mantenimiento:** Se facilitan las actualizaciones, pues el componente se centra en el estado de sus datos y React se encarga de reflejar los cambios en la pantalla.

# Uso del virtual DOM
Uno de los pilares fundamentales de React es el **Virtual DOM**. Se trata de una representación ligera e in-memory del DOM real.

## ¿Qué permite hacer?
**Eficiencia:** Realizar operaciones de comparación y actualización en memoria es mucho más rápido que manipular directamente el DOM del navegador, que es una operación costosa en términos de rendimiento.

**Aislamiento de cambios:** Cada vez que se actualiza el estado de un componente, React vuelve a renderizar (virtualmente) ese componente, generando una nueva versión del Virtual DOM.

# Proceso de Reconciliación
El proceso de actualización se conoce como **reconciliación** y consta de varios pasos:
1) **Generación del nuevo Virtual DOM:** Cuando se produce un cambio en el estado o en las propiedades (props), React ejecuta nuevamente el método `render` del componente, generando un nuevo árbol de elementos.
2) **Comparación (diffing):** React compara el nuevo Virtual DOM con el anterior para identificar las diferencias. Gracias a algoritmos de _diffing_ altamente optimizados, se determina exactamente qué partes del árbol han cambiado.
	- **Diffing**: El algoritmo diffing de React es la técnica que utiliza para determinar de forma eficiente qué cambios se deben aplicar al DOM real cuando hay una actualización en la interfaz.
3) **Cálculo de las actualizaciones mínimas:** Con la información de las diferencias detectadas, React calcula la cantidad mínima de modificaciones necesarias para actualizar el DOM real. Esto significa que, en lugar de reescribir toda la interfaz, solo se modifican los elementos que han cambiado.
4) **Actualización del DOM real:** Finalmente, React aplica estos cambios al DOM real, asegurándose de que la actualización sea lo más eficiente posible y sin comprometer la experiencia del usuario.

