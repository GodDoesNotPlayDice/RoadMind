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



