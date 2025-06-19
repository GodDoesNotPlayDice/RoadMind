Un **Higher-Order Component** es una función que recibe un componente y devuelve uno nuevo, “envolviendo” su lógica para **reutilizar** comportamiento o datos, entonces un **HOC** es una función que recibe un componente y devuelve un nuevo componente con lógica añadida.

_No forma parte de la API oficial de React: es un patrón que surge de la naturaleza composicional de sus componentes._
# Ejemplo corto

```ts
HOC = (WrappedComponent: React.ComponentType<P>) → React.ComponentType<P>
```

**WrappedComponent**: el componente original que tú creaste.
**HOC**: tu función “con envoltorio” que inyecta comportamiento (logging, autorización, temas, datos, etc.).
**Devuelve**: un componente que renderiza al WrappedComponent con props y lógica extra.


# HOC en Hooks
Hoy en día, en vez de envolver componentes con HOCs para compartir lógica, **React Hooks** te permiten extraer esa lógica en funciones reutilizables que llamas directamente dentro de tus componentes funcionales. Así evitas el “wrapper hell” y la complejidad de manejar refs o displayName.
