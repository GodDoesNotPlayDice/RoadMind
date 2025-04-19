En React con TypeScript, un componente funcional se define como una función que retorna TSX (una extensión de JSX) y se tipa generalmente usando `React.FC` o especificando explícitamente las props. 

Se recomienda definir interfaces o tipos para las propiedades que recibe el componente.

```tsx
import React from 'react';

interface GreetingProps {
  nombre: string;
}

const Greeting: React.FC<GreetingProps> = ({ nombre }) => {
  return <h1>¡Hola, {nombre}!</h1>;
};

export default Greeting;

```

Se define la interfaz `GreetingProps` para especificar que se espera una prop llamada `nombre` de tipo `string`.

Se utiliza `React.FC<GreetingProps>` para tipar el componente y tener autocompletado de props.

Siguiente paso saber de [[Props vs State]]

# JSX y TSX
**JSX** y **TSX** son muy parecidos: ambos te permiten escribir sintaxis tipo XML dentro de tu código JavaScript/TypeScript para describir la UI (por ejemplo con React). La diferencia clave es que TSX añade la potencia del tipado de TypeScript a esa sintaxis.

## Tipo de extensión
`.jsx` se usa cuando escribes JavaScript con JSX.
`.tsx` se usa cuando escribes TypeScript con JSX.

**JSX** = JavaScript + sintaxis XML, sin tipado estático.
**TSX** = TypeScript + sintaxis XML, con chequeo de tipos, autocompletado y all the goodies de TS.


## Tipado estático
En un archivo `.jsx` todo es JavaScript “puro”: no tienes comprobación de tipos en tiempo de compilación más allá de lo que te proporcione tu linter o tu configuración de Babel.

En un archivo `.tsx` el compilador de TypeScript valida tipos (propiedades de componentes, valores de variables, retornos de funciones, etc.), y te avisará de errores de incompatibilidad antes de ejecutar el código.

## Características
Con TSX puedes usar interfaces o type aliases para definir el shape de las props de tus componentes
[[Interfaces en Typescript]]
```ts
interface ButtonProps {
  label: string;
  onClick: () => void;
}

const Button = ({ label, onClick }: ButtonProps) => (
  <button onClick={onClick}>{label}</button>
);
```
En JSX puro tendrías que confiar en PropTypes u otro mecanismo de runtime, o bien renunciar al autocompletado/chequeo de tipos.

## Configuración del compilador
Para usar `.jsx` normalmente solo necesitas Babel o un bundler que lo soporte.
Para usar `.tsx` necesitas un `tsconfig.json` con `"jsx": "react-jsx"` (o la opción que elijas) y tener habilitado `allowJs` si vas a mezclar `.js/.jsx` y `.ts/.tsx`.

## Flujo de trabajo y mantenimiento
El tipado de **TSX** ayuda a escalar **aplicaciones grandes**, detectando errores comunes **(props mal nombradas, tipos incorrectos, imports duplicados).**

En proyectos **pequeños** o **prototipos rápidos** puede bastar con **JSX**, donde el setup suele ser más **ligero**.
