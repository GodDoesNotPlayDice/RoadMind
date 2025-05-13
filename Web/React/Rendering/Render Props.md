Un _render prop_ es una técnica para **compartir lógica** (estado, efectos, comportamientos) entre componentes sin acoplar la UI.

**¿Cuál es su función especial dentro de React?**  
Permite que un componente “genérico” delegue la parte de **renderizado** a quien lo use, pasando datos y callbacks a una función, y dejando que esa función devuelva el JSX concreto.

```tsx
// Toggle.tsx
import React, { useState } from 'react';

interface ToggleProps {
  /** children define la UI, recibiendo el estado 'on' y el callback 'toggle' */
  children: (on: boolean, toggle: () => void) => React.ReactNode;
}

const Toggle: React.FC<ToggleProps> = ({ children }) => {
  const [on, setOn] = useState(false);
  const toggle = () => setOn(o => !o);

  // Llamamos a la función children pasándole el estado y el callback
  return <>{children(on, toggle)}</>;
};

export default Toggle;

```

```tsx
// App.tsx
import React from 'react';
import Toggle from './Toggle';

const App: React.FC = () => (
  <div style={{ textAlign: 'center', marginTop: 40 }}>
    <h1>Ejemplo Render Prop / Toggle</h1>

    <Toggle>
      {(on, toggle) => (
        <button onClick={toggle}>
          {on ? '🟢 Encendido' : '⚪️ Apagado'}
        </button>
      )}
    </Toggle>
  </div>
);

export default App;

```

