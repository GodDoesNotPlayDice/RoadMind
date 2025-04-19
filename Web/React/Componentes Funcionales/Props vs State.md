Primero hay que saber que son los **Props** y **State** ya que se refieren a **dos mecanismos distintos para manejar y transmitir datos dentro de tus componentes**

|                     | **Props**                                | **State**                              |
| ------------------- | ---------------------------------------- | -------------------------------------- |
| **Origen**          | Vienen del componente **padre**          | Se definen **dentro** del componente   |
| **Mutabilidad**     | **Inmutables** (sólo lectura)            | **Mutables** vía `setState`/`useState` |
| **Responsabilidad** | **Configurar** al hijo                   | **Gestionar** datos que cambian ahí    |
| **Re-render**       | Cambio en props → render por parte padre | Cambio en state → render interno       |

## Cuando se ocupa cada uno
**Props**: Para pasar datos o funciones **hacia abajo** en la jerarquía de componentes y cuando el hijo no necesita cambiar esos datos.

**State**: Para datos que el componente **controla y modifica** a lo largo del tiempo (formularios, contadores, toggles, etc.). y cuando un valor interno debe provocar actualizaciones de UI al cambiar.
# Props
Son los “**parámetros**” que un componente recibe de su padre.
Son el mecanismo por el cual un componente de **React recibe datos y comportamientos desde su componente padre**.

Hijo (componente funcional): `User.tsx`
```tsx
import React from 'react';

interface UserProps {
firstName: string;
lastName: string;
}

const User: React.FC<UserProps> = ({ firstName, lastName }) => {
	return (
		<div>
			<h1>
				{firstName} {lastName}
			</h1>
		</div>
	);
};
export default User;
```

Padre: `App.tsx`
```tsx
import User from "./User"
function App() {
	return (
		<>
			<div>
				<h1>App</h1>
					<User firstName="John" lastName="Doe" />
			</div>
		</>
	)
}

export default App
```

## Características
**Inmutables** dentro del componente que las recibe.
Se definen al invocar el componente
```tsx
<User firstName="John" lastName="Doe" />
```

# State
Es la **propia memoria interna** de un componente. Guarda datos que **cambian** a lo largo del tiempo, generalmente en respuesta a interacciones del usuario

## Características 
**Mutables**, pero sólo a través de las funciones que React provee (`useState`, `setState`).
Definidos **dentro** del componente:
```tsx
const [contador, setContador] = useState(0);
```
Cada vez que cambian, React **vuelve a renderizar** ese componente para reflejar los nuevos valores.


# Ejemplo de uso completo
Combinación simple entre **State** y **Props**

`User.tsx` : Hijo
```tsx
import React from "react";

interface UserProps {
  edad: number;
  nombre: string;
}

const User: React.FC<UserProps> = ({ edad, nombre }) => {
  return (
    <div>
      <p>
        Hola soy {nombre} y tengo {edad}
      </p>
    </div>
  );
};

export default User;

```

`App.tsx` Padre
```tsx
import User from "./User";
import { useState } from "react";

function App() {
  const [numero_edad, setCount] = useState(25);
  return (
    <>
      <div className="flex justify-center">
        <div className="flex flex-col gap-2.5">
          <h1 className="text-center text-4xl">App</h1>

          <User nombre="Juan" edad={numero_edad} />

          <button
            className="bg-blue-500 text-white p-2 rounded"
            onClick={() => setCount(numero_edad + 1)}
          >
            Agregar edad
          </button>
        </div>
      </div>
    </>
  );
}

export default App;
```


