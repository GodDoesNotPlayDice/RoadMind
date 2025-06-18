Un **Higher-Order Component** es una función que recibe un componente y devuelve uno nuevo, “envolviendo” su lógica para **reutilizar** comportamiento o datos, entonces un **HOC** es una función que recibe un componente y devuelve un nuevo componente con lógica añadida.

_No forma parte de la API oficial de React: es un patrón que surge de la naturaleza composicional de sus componentes._


# Ejemplo corto

```ts
HOC = (WrappedComponent: React.ComponentType<P>) → React.ComponentType<P>
```

**WrappedComponent**: el componente original que tú creaste.
**HOC**: tu función “con envoltorio” que inyecta comportamiento (logging, autorización, temas, datos, etc.).
**Devuelve**: un componente que renderiza al WrappedComponent con props y lógica extra.
# Firma genérica en Typescript
Para que nuestro HOC sea totalmente tipado y genérico, podemos usar esta firma.
```ts
import React from 'react';

type ComponentType<P> = React.ComponentType<P>;

/**
 * withEnhancement: HOC genérico
 * @param WrappedComponent — componente original
 * @returns nuevo componente que acepta las mismas props P
 */
function withEnhancement<P extends object>(
  WrappedComponent: ComponentType<P>
): React.FC<P> {
  const EnhancedComponent: React.FC<P> = (props) => {
    // Aquí va la lógica adicional
    return <WrappedComponent {...props} />;
  };

  // ¡Para facilitar debugging!
  EnhancedComponent.displayName =
    `withEnhancement(${WrappedComponent.displayName || WrappedComponent.name || 'Component'})`;

  return EnhancedComponent;
}
```
