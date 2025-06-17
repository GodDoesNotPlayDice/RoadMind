En React (y en JavaScript en general), un **evento** es un objeto que representa que algo ha ocurrido en el sistema o en la interfaz de usuario: un clic, la pulsación de una tecla, el envío de un formulario, la carga de un recurso, etc.


```tsx
import React from 'react';

const EventoTSX: React.FC = () => {
  // El evento tiene tipo de TypeScript: React.MouseEvent<HTMLButtonElement>
  const handleClick = (event: React.MouseEvent<HTMLButtonElement>) => {
    console.log("¡Hiciste clic!", event);
    alert("¡Evento manejado en TSX!");
  };

  return s(
    <div>
      <h1>Ejemplo de Evento</h1>
      <button onClick={handleClick}>Haz clic aquí</button>
    </div>
  );
};

export default EventoTSX;
```
