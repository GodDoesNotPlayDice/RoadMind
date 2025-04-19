React tiene un poderoso modelo de composición, y se recomienda utilizar la **composición** en lugar de la **herencia** para **reutilizar el código entre los componentes.**

# ¿Que es la herencia y su problema en react?
En POO es un mecanismo por el cual una clase “hijo” extiende el comportamiento de una clase “padre”, heredando métodos y propiedades.

**Ejemplo en react**
```jsx
class Button extends React.Component { /*…*/ }
class FancyButton extends Button { /* hereda toda la lógica de Button */ }
```

## Los problemas

### Acopla fuertemente los componentes.
El componente hijo depende directamente de la implementación interna del padre (métodos, estado, propiedades privadas).

**Consecuencias:**
- **Difícil mantenimiento:** Un cambio en la clase base puede romper múltiples subclases.
- **Baja reusabilidad:** No puedes extraer fácilmente la lógica común para usarla en otros componentes que no compartan toda la jerarquía.
- **Testing complejo:** Para probar un hijo, debes entender y mockear la lógica de la clase padre completa.

**Ejemplo del problema**
```jsx
class Button extends React.Component {
  toggleActive() { /* cambia un state interno */ }
  render() { /* … */ }
}
class FancyButton extends Button {
  componentDidMount() {
    // Llama a un método privado del padre
    this.toggleActive();
  }
  render() { /* mezcla lógica del padre + estilos extra */ }
}

```
Si renombraras o cambiaras la implementación de `toggleActive`, **todos** los hijos que la usan tendrían que actualizarse.

### Relaciones “es‑un” poco naturales en UI
En herencia clásica, `FancyButton` **es un** `Button`.

Los componentes de interfaz suelen combinar comportamientos de forma **especializada** (e.g., un botón con tooltip, un botón con contador, un botón con confirmación), no como una jerarquía rígida.

Al forzar “es‑un”, terminas con árboles de clases profundos que no reflejan la forma en que quieres **componer** la UI (más bien es **tiene‑un**, “un botón tiene un tooltip”, etc.).

**Ejemplo de conflicto conceptual:**
- ¿`IconButton` extiende de `FancyButton` o viceversa?
- ¿`TooltipButton` extiende de `IconButton`?

Con herencia, tendrías que elegir una única línea jerárquica, en lugar de mezclar comportamientos de forma adecuada.

### Rendimiento y complejidad innecesarios

#### Sobrecarga de clases ES6
- Cada componente basado en clase crea una cadena de prototipos que React debe gestionar.
- Las funciones de binding (`this.method = this.method.bind(this)`) añaden trabajo extra en el constructor.

#### Reconcilación de React:
- React está optimizado para componentes **funcionales** y hooks. Añadir herencia no acelera ninguna de las fases de diffing o renderizado.

#### Complejidad cognitiva
- Tienes que seguir la cadena de herencia para entender de dónde viene cada método o estado.
- En debugging, un simple error puede “viajar” varias capas hacia arriba en la jerarquía, haciendo más difícil aislar la causa.

#### Alternativas más ligeras
- **Hooks** y **HOCs** aíslan la lógica reutilizable sin modificar la jerarquía de componentes.
- **Render props** inyectan comportamiento en tiempo de render, sin necesidad de clases adicionales.