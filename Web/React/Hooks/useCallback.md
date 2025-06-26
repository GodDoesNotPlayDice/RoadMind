El hook `useCallback` te permite memorizar (cachear) funciones para que no se vuelvan a crear en cada render, siempre y cuando sus dependencias no cambien. Esto es muy útil cuando pasas callbacks a componentes hijos memoizados, para evitar renders innecesarios.

Ejemplo de un componente que incrementa un contador y tiene un botón “Reset” que se memoiza con `useCallback`.

```tsx
import React, { useState, useCallback } from 'react';

const Counter: React.FC = () => {
  const [count, setCount] = useState<number>(0);

  // Función memoizada sin dependencias: se creará sólo una vez
  const reset = useCallback(() => {
    setCount(0);
  }, []); 

  return (
    <div>
      <p>Contador: {count}</p>
      <button onClick={() => setCount(c => c + 1)}>Incrementar</button>
      <button onClick={reset}>Resetear</button>
    </div>
  );
};

export default Counter;
```

Como `reset` está declarado con `[]`, **nunca** se recrea salvo el primer render.
Si lo pasáramos a un hijo memoizado, React comprobaría que la referencia de `reset` no cambia y no forzaría un nuevo render.


