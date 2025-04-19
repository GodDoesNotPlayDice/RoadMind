Es la capacidad de React para mostrar u ocultar componentes o elementos **según el estado** (state) o las **props** de tu aplicación. Funciona igual que en JavaScript: usas `if`, el operador ternario (`?:`), el operador lógico `&&`, etc., para decidir qué renderizar. [[Expressions and Operators]]

- **Mantén la lógica simple**: si un componente tiene mucha condición, extrae subcomponentes.
- **Evita expresiones muy anidadas**: pre‐calcula variables o usa funciones auxiliares.
- **Usa nombres claros** para estados (`isLoading`, `hasError`, `showModal`, etc.).
- **Componente por responsabilidad**: un componente debe encargarse de una sola parte de UI.

|Técnica|Cuándo usarla|Sintaxis básica|
|---|---|---|
|**If/else antes del return**|Lógica compleja, múltiples ramas|Bloque `if` en el cuerpo de la función|
|**Operador ternario**|Dos opciones claras (true / false)|`{condición ? <A/> : <B/>}`|
|**Operador lógico `&&`**|Mostrar algo sólo si la condición es true|`{condición && <Componente/>}`|
|**Switch/case**|Varias opciones discretas (>=3 casos)|`switch(valor) { case 'x': return <X/>; … }`|
# Ejemplos

## Ejemplos con operadores ternarios

```tsx
import React, { useState } from 'react';

export function Greeting() {
  const [loggedIn, setLoggedIn] = useState(false);

  return (
    <div>
      {loggedIn
        ? <h1>¡Bienvenido de nuevo!</h1>
        : <h1>Por favor, inicia sesión.</h1>
      }

      <button onClick={() => setLoggedIn(!loggedIn)}>
        {loggedIn ? 'Cerrar sesión' : 'Iniciar sesión'}
      </button>
    </div>
  );
}
```


## Mostrar sólo si… (short‑circuit `&&`)

```tsx
import React, { useState } from 'react';

export function Notifications() {
  const [hasNotifications, setHasNotifications] = useState(true);
  const notifications = ['Tarea 1 pendiente', 'Reunión a las 3pm'];

  return (
    <div>
      <h2>Notificaciones</h2>
      {hasNotifications && (
        <ul>
          {notifications.map((n, i) => <li key={i}>{n}</li>)}
        </ul>
      )}
      {!hasNotifications && <p>No hay notificaciones.</p>}
      <button onClick={() => setHasNotifications(!hasNotifications)}>
        {hasNotifications ? 'Ocultar' : 'Mostrar'} notificaciones
      </button>
    </div>
  );
}
```

## If/else antes del return (más organizado)

```tsx
import React, { useState } from 'react';

export function StatusMessage() {
  const [status, setStatus] = useState<'loading'|'error'|'ok'>('loading');
  let contenido;

  if (status === 'loading') {
    contenido = <p>Cargando datos...</p>;
  } else if (status === 'error') {
    contenido = <p>Error al cargar. Intenta de nuevo.</p>;
  } else {
    contenido = <p>Datos cargados correctamente.</p>;
  }

  return (
    <div>
      <h2>Estado de la petición</h2>
      {contenido}
      <button onClick={() => setStatus('loading')}>Cargar</button>
      <button onClick={() => setStatus('error')}>Simular error</button>
      <button onClick={() => setStatus('ok')}>Simular éxito</button>
    </div>
  );
}
```


