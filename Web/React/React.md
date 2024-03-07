## Estructura base de React

esta es la base de cualquier componente de React usando TS.

```tsx
import React from "react";

interface TitleProps{
	name : string;
}

export const Title: React.FC<TitleProps> = ({name}) => {
	return (
		<h1>Hola bienvenido {name}</h1>
	
	)
}

```


## Manejo de los elementos en React

### Sin uso del estado

Sin uso del estado estamos haciendo es limitar la capacidad de renderizado y reactividad al elemento afectado, sin embargo, esto nos puede servir en algunos casos donde no necesitemos una reactividad con algún o mismo elemento.

Ejemplo: un nav que tenga los elementos ocultos y haya un botón que solo haga show y hidde de los elementos.

- Ventajas: Simplifica la lógica del componente y mejora el rendimiento al no tener que rastrear y actualizar el estado.
- Desventajas: Limita la capacidad de crear interfaces de usuario dinámicas y reactivas.


### Con uso del estado

 Con el uso del estado los componentes pueden mantener y actualizar datos de forma dinámica. Esto permite que los elementos de la interfaz de usuario respondan a eventos y cambios de datos en la aplicación.

Ejemplo: Un contador que incrementa su valor cada vez que se hace clic en un botón. El estado del contador se actualiza cada vez que se hace clic, y React se encarga de volver a renderizar el componente con el nuevo valor.

- Ventajas: Permite una gestión dinámica de datos y una interfaz de usuario interactiva.
- Desventajas: Puede aumentar la complejidad del código y el rendimiento si no se utiliza correctamente.
#### Hooks
En React, los "hooks" son funciones especiales que te permiten utilizar el estado y otras características de React sin tener que escribir una clase.

Los hooks proporcionan una forma más simple y efectiva de compartir lógica entre componentes, reutilizar código y manejar el ciclo de vida del componente.

Existen 3 tipos de Hooks:
 
##### useState 
 Este hook permite agregar estado a componentes funcionales. Te permite declarar variables de estado y actualizarlas, similar a cómo funcionaba `this.state` en componentes de clase.
```tsx
import React, { useState } from 'react';

export const Contador: React.FC = () => {
  const [count, setCount] = useState<number>(0);

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>Click me</button>
    </div>
  );
};
```
