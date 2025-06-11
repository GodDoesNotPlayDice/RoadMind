Un **ref** en React es un objeto mutable que te da acceso directo e imperativo a un elemento del DOM o a la instancia de un componente, útil para tareas como enfocar un input, medir dimensiones o integrar librerías externas sin pasar por props o state.

Usa **state/props** y **callbacks** para la mayoría de tus interacciones. Recurre a **refs** **solo** cuando necesites:
- Control imperativo (focus, play, scroll).
- Integración con librerías que requieren el nodo DOM.
- Guardar valores mutables que **no** afecten la UI (temporizadores, contadores internos).

## Que utilidades tiene
1) **Proveer un “puente” imperativo al DOM o a la instancia de un componente**
    - React mantiene tu UI de forma declarativa, pero a veces necesitas invocar métodos nativos (p. ej., `focus()`, `play()`, medir tamaño). Un ref es ese puente que te da acceso directo a ese nodo.
2) **Persistir un valor mutable entre renderizados sin causar re-renderizados**
    - A diferencia del estado, cambiar `ref.current` no provoca que React vuelva a dibujar el componente, por lo que sirve como “cajón” para guardar cualquier dato mutable (temporizadores, contadores de renders, referencias a librerías externas) que deba sobrevivir entre renders.

## No resolver todo con Ref
No se debería resolver todo con `ref` ya que react funciona de manera declarativa por lo que esta diseñado para sincronizar la UI con el estado y las props de forma predecible. Si accedes y mutas directamente el DOM con refs, te saltas ese flujo y el código se vuelve más difícil de seguir y depurar. **Romper el flujo declarativo**

Al cambiar el DOM “por fuera” (imperativamente), React no sabe que algo cambió, por lo que no optimiza ni actualiza eficientemente otros componentes relacionados. **Pierdes beneficios del ciclo de vida y la reconciliación**

El uso excesivo de refs tiende a dispersar la lógica de interacción y estado en muchos puntos, en lugar de centralizarla en un estado controlado. Esto hace que sea más fácil introducir bugs al modificar o refactorizar. **Complican el mantenimiento y la escalabilidad**

Con state y props puedes, por ejemplo, deshabilitar un botón hasta que el usuario escriba algo válido, mostrar mensajes de error en tiempo real o disparar efectos cuando cambia un valor. Con refs pierdes esa reactividad. **No aprovechas validaciones ni renderizado condicional**

El código que depende de refs suele ser más imperativo y menos predecible, lo que dificulta escribir tests automáticos para cubrir todos los casos.**Más difícil de testear**

## Formas de crear un Ref

### Clases (Antigua)
`createRef()` se llama **una sola vez** (habitualmente en el constructor o como propiedad de la clase), la referencia permanece igual en cada render.
```tsx
import React, { Component, createRef } from 'react';

class MiComponente extends Component {
  inputRef = createRef<HTMLInputElement>();  // ⬅ se define fuera de render

  focusInput = () => {
    this.inputRef.current?.focus();
  }

  render() {
    return (
      <>
        <input ref={this.inputRef} placeholder="Clase" />
        <button onClick={this.focusInput}>Enfocar</button>
      </>
    );
  }
}

```


### Hook (Moderna)
`useRef` **memoriza** el mismo objeto `{ current: ... }` entre renders. Además de referenciar DOM, puedes usarlo para guardar cualquier valor mutable (como el contador de renders, un temporizador, etc.) sin disparar nuevos renders.
```tsx
import { useRef } from 'react';

export function MiComponenteFuncional() {
  const inputRef = useRef<HTMLInputElement | null>(null); // ⬅ se crea al montar y no se recrea

  const focusInput = () => {
    inputRef.current?.focus();
  };

  return (
    <>
      <input ref={inputRef} placeholder="Funcional" />
      <button onClick={focusInput}>Enfocar</button>
    </>
  );
}
```


## Problema `state` y `ref` 
Como bien sabemos no podemos solucionar todo con `ref` y este un ejemplo simple de como resolver un problema con `state` de manera eficiente en vez de con `ref` obteniendo el mismo resultado en ambas.

**¿Cuando usar?**
- **State/controlado**: formularios complejos, validaciones en vivo, sincronización continua.
- **useRef/no controlado**: lecturas puntuales del DOM, integraciones con terceros, rendimiento si no te importa no tener el valor intermedio en React.

### Usando `state`
- El valor del `<input>` vive en el estado de React.
- Cada vez que cambias el texto, disparas `setValue`, que vuelve a renderizar.
- Al pulsar “Enviar”, usas directamente ese estado.
```tsx
import { useState } from 'react';

export function ControlledForm() {
  const [value, setValue] = useState('');

  const handleChange = (e: React.ChangeEvent<HTMLInputElement>) => {
    setValue(e.target.value);
  };

  const handleSubmit = () => {
    alert(`Has escrito: ${value}`);
  };

  return (
    <div>
      <input
        type="text"
        value={value}               // ← valor controlado por state
        onChange={handleChange}     // ← callback para actualizar state
        placeholder="Escribe algo…"
      />
      <button onClick={handleSubmit}>
        Enviar
      </button>
    </div>
  );
}
```

**Ventaja**
- Siempre tienes el valor en React; sirve para validación en tiempo real, forms complejos, deshabilitar botones, etc.
- Sigue el flujo de datos React (props/state).

### Solución imperativa `ref`
- No guardamos el valor en estado ni re-renderizamos en cada tecla.
- Creamos un ref al nodo DOM y, al enviar, leemos `inputRef.current.value`.


```tsx
import { useRef } from 'react';

export function UncontrolledForm() {
  const inputRef = useRef<HTMLInputElement | null>(null);

  const handleSubmit = () => {
    const text = inputRef.current?.value ?? '';
    alert(`Has escrito: ${text}`);
  };

  return (
    <div>
      <input
        type="text"
        ref={inputRef}              // ← acceso directo al DOM
        placeholder="Escribe algo…"
      />
      <button onClick={handleSubmit}>
        Enviar
      </button>
    </div>
  );
}

```

