`useState` es un **Hook** de React que te permite añadir y manejar **estado** en componentes funcionales. Antes solo podías hacerlo con componentes de clase, pero con los hooks, ya no es necesario.

# Uso básico
```tsx
import { useState } from 'react';

function Contador() {
  const [contador, setContador] = useState(0);

  return (
    <div>
      <p>Has hecho clic {contador} veces</p>
      <button onClick={() => setContador(contador + 1)}>
        Incrementar
      </button>
    </div>
  );
}
```

`useState(0)`: Inicializa el estado con valor `0`.
`[contador, setContador]`: Crea dos cosas `contador` (el valor actual) y `setContador` (una función para cambiarlo)
`setContador(contador + 1)`: Cambia el valor al hacer click.

## Detalles
 1) `useState` siempre devuelve un **array** con (valor, funciónActualizadora)
 2) Puedes usar `useState` varias veces en un mismo componente para manejar múltiples estados distintos. 


