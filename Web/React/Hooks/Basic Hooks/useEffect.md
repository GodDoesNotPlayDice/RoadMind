`useEffect` te permite ejecutar código **después** de que React haya renderizado el componente. Es ideal para:
- Hacer peticiones HTTP (fetch/axios).
- Suscribirte a eventos (por ejemplo, `addEventListener`).
- Configurar timers (`setTimeout`, `setInterval`).
- Limpiar suscripciones o timers cuando el componente se desmonte.

```tsx
import { useEffect, useState } from 'react';

function MiComponente() {
  const [dato, setDato] = useState(null);

  useEffect(() => {
    // Este código corre tras el primer renderizado
    console.log('¡Componente montado!');

    // Opcional: limpiar al desmontar
    return () => {
      console.log('¡Componente se desmonta!');
    };
  }, []); // ← array de dependencias vacío
}
```

- **Primer parámetro**: función que contiene el efecto.
- **Valor de retorno (opcional)**: función de limpieza (cleanup)
- **Segundo parámetro**: array de dependencias ; controla cuando se re-ejecuta el efecto.

## Dependencias
Es el **cuando** se ejecuta el estado, el efecto se puede ejecutar por **montaje** ; **actualización** ; **dependencia** ; 

### Montaje
Este se refiere al **efecto** después de cada **re-renderizado** de componente `useEffect(fn)`, por lo que
- Se invoca tras **cada** render: tanto la **primera vez** como **cada** actualización de estado o props.
- No tiene array de dependencias, así que React no “fija” ningún control que lo frene.

```tsx
  useEffect(() => {
    console.log('🔥 Efecto SIN dependencias: cada render');
  });
  ```
### Actualización
Se invoca **solo** tras el **primer** render (montaje).
- Las dependencias están vacías, por lo que React no volverá a ejecutarlo aunque cambie cualquier estado o prop.
- Si tu función `fn` retorna un cleanup, ese cleanup se ejecuta únicamente **cuando el componente se desmonta**.
```tsx
  useEffect(() => {
    console.log('🌱 Efecto CON []: solo al montar');
    return () => {
      console.log('🧹 Cleanup CON []: al desmontar');
    };
  }, []);
  ```
  
### Dependencia
Este solo se ejecuta al primer render **mount** y luego solo se volverá a ejecutar cuando alguna dependencia haya cambiado, ejemplo el "contador".
```tsx
  useEffect(() => {
    console.log(`⏱️ Efecto CON [contador]: contador = ${contador}`);
    return () => {
      console.log(`🔄 Cleanup CON [contador]: antes de re-ejecutar o desmontar (contador = ${contador})`);
    };
  }, [contador]);
  ```

