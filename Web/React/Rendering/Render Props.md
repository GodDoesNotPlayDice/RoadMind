Un _render prop_ es una técnica para **compartir lógica** (estado, efectos, comportamientos) entre componentes sin acoplar la UI.

**¿Cuál es su función especial dentro de React?**  
Permite que un componente “genérico” delegue la parte de **renderizado** a quien lo use, pasando datos y callbacks a una función, y dejando que esa función devuelva el TSX concreto.

## Ejemplo con Render Props

**Ejemplo**
```
src/
├─ components/
│  ├─ Wrapper.tsx
│  ├─ Counter1.tsx
│  └─ Counter2.tsx
└─ App.tsx
```

En simples palabras lo que sucede aquí es que usamos una clase para definir el funcionamiento de un componente, literalmente lo cargamos con la logíca.
```tsx
// components/Wrapper.tsx
import React from "react";

//
// Definimos la forma de los datos que pasaremos al render prop.
//
interface WrapperRenderProps {
  count: number;
  incCount: () => void;
}

//
// Props que recibe nuestro Wrapper: una sola prop “render”
// que es una función que recibe { count, incCount } y devuelve JSX.
//
interface WrapperProps {
  render: (props: WrapperRenderProps) => React.ReactNode;
}

interface WrapperState {
  count: number;
}

export class Wrapper extends React.Component<WrapperProps, WrapperState> {
  state: WrapperState = { count: 0 };

  // Método para incrementar el contador
  incCount = () => {
    this.setState((prev) => ({ count: prev.count + 1 }));
  };

  render() {
    // Llamamos a this.props.render y le pasamos { count, incCount } 
    return (
      <>
        {this.props.render({
          count: this.state.count,
          incCount: this.incCount,
        })}
      </>
    );
  }
}
```

Los componentes solo contendrán la "cascara" de la lógica que se les implementara.  
```tsx
// components/Counter1.tsx
import React from "react";

// Props que recibe Counter1
interface Counter1Props {
  count: number;
  incCount: () => void;
}

export const Counter1: React.FC<Counter1Props> = ({ count, incCount }) => {
  return (
    <div>
      <p>Counter1: {count}</p>
      <button onClick={incCount}>Incrementar Counter1</button>
    </div>
  );
};

```

```tsx
// components/Counter2.tsx
import React from "react";

// Props que recibe Counter2
interface Counter2Props {
  count: number;
  incCount: () => void;
}

export const Counter2: React.FC<Counter2Props> = ({ count, incCount }) => {
  return (
    <div>
      <p style={{ color: "purple" }}>Counter2: {count}</p>
      <button style={{ color: "purple" }} onClick={incCount}>
        Incrementar Counter2
      </button>
    </div>
  );
};

```

La lógica es implementada dentro del **Objeto** wrapper 
```tsx
// App.tsx
import React from "react";
import { Wrapper } from "./components/Wrapper";
import { Counter1 } from "./components/Counter1";
import { Counter2 } from "./components/Counter2";

export const App: React.FC = () => {
  return (
    <div style={{ padding: 20 }}>
      {/* Primer Wrapper: render prop que renderiza Counter1 */}
      <Wrapper
        render={({ count, incCount }) => {
          return <Counter1 count={count} incCount={incCount} />;
        }}
      />

      {/* Segundo Wrapper: render prop que renderiza Counter2 */}
      <Wrapper
        render={({ count, incCount }) => {
          return <Counter2 count={count} incCount={incCount} />;
        }}
      />
    </div>
  );
};

```

**Verboso / Boilerplate**
- Hay que definir por fuerza interfaces (`WrapperProps`, `WrapperState`, `WrapperRenderProps`) y anidar la llamada a `this.props.render(...)` dentro de _render()_.
- Cada vez que consumas el componente `Wrapper`, debes escribir `<Wrapper render={ props => (…) } />`, lo cual puede volverse tedioso.

**Anidamiento de JSX (“Callback Hell”)**
- Si en lugar de un solo render prop tuvieras varios (por ejemplo, un `AuthProvider` que también use render props, luego un `DataProvider`, etc.), terminarías con varias capas de anidación
```tsx
<AuthProvider render={(user) => (
  <DataProvider render={(data) => (
    <Wrapper render={({ count, incCount }) => (
      <App data={data} user={user} count={count} incCount={incCount} />
    )} />
  )} />
)} />

```
## Ejemplo con custom hooks
A partir de React 16.8+, la forma más sencilla de compartir lógica de estado y efectos es usando **Hooks personalizados**. Vamos a reescribir el mismo ejemplo (dos contadores independientes) sin Render Props ni componentes de clase, usando sólo funciones y Hooks.


```
src/
├─ hooks/
│  └─ useCounter.ts
├─ components/
│  ├─ Counter1.tsx
│  ├─ Counter2.tsx
│  └─ CounterDisplay.tsx
└─ App.tsx
```

```tsx
// hooks/useCounter.ts
import { useState, useCallback } from "react";

interface UseCounterReturn {
  count: number;
  incCount: () => void;
}

export function useCounter(initial: number = 0): UseCounterReturn {
  const [count, setCount] = useState<number>(initial);

  // useCallback para memorizar la función y evitar re-creaciones innecesarias.
  const incCount = useCallback(() => {
    setCount((prev) => prev + 1);
  }, []);

  return { count, incCount };
}
```

`useCounter` es un Hook personalizado que expone `{ count, incCount }`.

Internamente usa `useState` para el contador y `useCallback` para memorizar la función de incremento (no esencial, pero recomendado en casos reales).

```tsx
// components/CounterDisplay.tsx
import React from "react";

export interface CounterDisplayProps {
  label: string;
  count: number;
  incCount: () => void;
  color?: string;
}

export const CounterDisplay: React.FC<CounterDisplayProps> = ({
  label,
  count,
  incCount,
  color = "black",
}) => {
  return (
    <div style={{ marginBottom: 16 }}>
      <p style={{ color }}>
        {label}: {count}
      </p>
      <button style={{ color }} onClick={incCount}>
        Incrementar {label}
      </button>
    </div>
  );
};
```

`CounterDisplay` es un componente puramente de presentación (presentation-only).   Recibe:
- `label` (cadena que identifica el contador),
- `count` (número),
- `incCount` (función para incrementar),
- `color` (opcional, para cambiar estilo).

No gestiona ningún estado propio; sólo pinta lo que le pasan por props.

`components/Counter1.tsx`
```tsx
// components/Counter1.tsx
import React from "react";
import { useCounter } from "../hooks/useCounter";
import { CounterDisplay } from "./CounterDisplay";

export const Counter1: React.FC = () => {
  const { count, incCount } = useCounter(0);

  return <CounterDisplay label="Counter1" count={count} incCount={incCount} />;
};

```

`components/Counter2.tsx`
```tsx
// components/Counter2.tsx
import React from "react";
import { useCounter } from "../hooks/useCounter";
import { CounterDisplay } from "./CounterDisplay";

export const Counter2: React.FC = () => {
  const { count, incCount } = useCounter(0);

  // Aquí cambias el color a púrpura para diferenciarlo
  return (
    <CounterDisplay
      label="Counter2"
      count={count}
      incCount={incCount}
      color="purple"
    />
  );
};

```

`App.tsx`
```tsx
// App.tsx
import React from "react";
import { Counter1 } from "./components/Counter1";
import { Counter2 } from "./components/Counter2";

export const App: React.FC = () => {
  return (
    <div style={{ padding: 20 }}>
      <Counter1 />
      <Counter2 />
    </div>
  );
};

```

### Ventajas de usar los custom hooks
**Simplicidad y Concisión**
- No necesitas definir clases, constructores ni estados en forma de `this.state`.
- El Hook `useCounter` encapsula la lógica de estado y `useCallback`. Queda todo en pocas líneas.
**Separación Lógica / UI**
- El Hook (`useCounter`) se encarga _únicamente_ de la parte de estado.
- `CounterDisplay` —el componente de presentación— sólo muestra los datos que recibe.
- Si en otro componente necesitas un contador, basta con importar `useCounter(…)` y pasarlo a cualquier componente que cumpla la UI (no tienes que replicar un “Wrapper” con render props).
**Tipado más Natural**
- `useCounter` retorna una tupla u objeto con el estado. No hace falta definir una interfaz para el “render prop”.
- Los componentes funcionales usan `React.FC<…>` y definen directamente sus props. Esto tiende a ser menos verboso que declarar `WrapperProps`, `WrapperState`, etc.

#### Evitar callback-hell
- Con render props, cada proveedor enlazado tenía su propio `<Componente render={…} />`. Con Hooks, sólo importas `useCounter` o el custom Hook que necesites y lo consumes inline (sin anidar JSX)
- El flujo de datos es más plano y más fácil de leer.

#### Comparación

| Característica       | Render Props (clase/función)                                                                                                     | Hooks + Funcionales                                                                                                         |
| -------------------- | -------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------- |
| Verbosidad           | 🔴 Hay que definir interfaces de props, estado y render prop.                                                                    | 🟢 Hook + componentes puros, mucho más conciso.                                                                             |
| Anidamiento          | 🔴 Si combinas varios render props o HOCs, terminas con “JSX hell”.                                                              | 🟢 Se usa el Hook directamente, sin anidamientos complejos.                                                                 |
| Separación lógica/UI | 🔴 Se “rompe” el flujo: lógica en Wrapper (clase), UI en el callback.                                                            | 🟢 Lógica en el Hook, UI en componentes separados o inline.                                                                 |
| Tipado TSX           | 🔴 Tienes que definir manualmente varios `interface` / `type`.                                                                   | 🟢 Sólo defines tipos de las props de cada componente y de los retornos del Hook.                                           |
| Mantenimiento        | 🔴 Si quieres cambiar algo en la lógica (p. ej. agregar `isLoading`), tienes que modificar Wrapper y la firma de la render prop. | 🟢 Cambio en el Hook, los componentes de UI sólo reciben nuevas props, casi transparente.                                   |
| Curva de aprendizaje | 🟠 Si vienes de POO, puede resultar familiar, pero `this` y `componentDidMount` confunden a algunos.                             | 🟢 Hooks tienen una curva de “aprender bien las reglas” (dependencies, etc.), pero una vez entendidos, todo es más directo. |
| Compatibilidad       | 🔴 Basado en clases o funciones antiguas; ya no es “la forma preferida” en React moderno.                                        | 🟢 Patrón actual; fomentado por la documentación oficial de React 17/18.                                                    |
