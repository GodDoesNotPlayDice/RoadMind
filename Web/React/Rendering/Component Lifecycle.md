[Ciclo de vida de los efectos reactivos](https://react.dev/learn/lifecycle-of-reactive-effects)
[Video explicativo](https://www.youtube.com/watch?v=kKVVan3EGoU)
# Fases del Ciclo
Los componentes React tienen un ciclo de vida que consta de tres fases: **montaje, actualización y desmontaje** junto con varios **"métodos de ciclo de vida"** que puede anular para ejecutar código en momentos particulares del proceso.

## Mounting
Es el momento en que el componente aparece por primera vez en la pantalla.
- **Metáfora**: Un tendero monta su puesto de frutas. Coloca **peras** y **manzanas** en el mostrador para empezar a vender.
- **React**: Se crea la instancia del componente, se ejecuta el **código de inicialización** (por ejemplo, leer datos, suscribirse a un servicio).
## Updating
Ocurre cada vez que cambian sus **props** o su **state**.
- **Metáfora**: Llegan clientes y compran frutas, o llegan cajas nuevas
	- Si compran peras, el tendero retira peras del puesto.
	- Si llega una entrega nueva, repone manzanas.
- **React**: El componente “re-renderiza” para reflejar los nuevos datos, puedes usar `useEffect` con dependencias para reaccionar a esos cambios.
## Unmounting
Cuando el componente deja de mostrarse en pantalla.
- **Metáfora**: Al cerrar el puesto, el tendero guarda las peras y manzanas que quedan y limpia el mostrador.
- **React** Se ejecuta la **función de limpieza** de `useEffect` (si la has definido), Se liberan suscripciones, timers, conexiones, etc.

## Ejemplo 

```tsx
import React, { useState, useEffect } from 'react';

interface CestaFrutasProps {
  perasIniciales: number;
  manzanasIniciales: number;
}

const CestaFrutas: React.FC<CestaFrutasProps> = ({
  perasIniciales,
  manzanasIniciales,
}) => {
  // Estado interno con tipado explícito
  const [peras, setPeras] = useState<number>(perasIniciales);
  const [manzanas, setManzanas] = useState<number>(manzanasIniciales);

  // 1. Montaje: solo al montar y desmontar
  useEffect(() => {
    console.log(
      `👍 Puesto montado: ${peras} peras y ${manzanas} manzanas disponibles.`
    );
    return () => {
      console.log('🧹 Puesto desmontado: recogiendo frutas sobrantes.');
    };
  }, []); // [] = efecto solo en mount y unmount

  // 2. Actualización: cada vez que cambie peras o manzanas
  useEffect(() => {
    console.log(`🔄 Actualización: ahora hay ${peras} peras y ${manzanas} manzanas.`);
  }, [peras, manzanas]);

  return (
    <div>
      <h2>Cesta de Frutas</h2>
      <p>Peras: {peras} 🍐</p>
      <p>Manzanas: {manzanas} 🍎</p>
      <button onClick={() => setPeras(peras - 1)} disabled={peras <= 0}>
        Vender 1 pera
      </button>
      <button onClick={() => setManzanas(man zanas + 2)}>
        Llegan 2 manzanas
      </button>
    </div>
  );
};

export default CestaFrutas;

```

**Montaje** (primer `useEffect` con `[]`): se abre el puesto y se registra el stock inicial; al desmontar, limpia.

**Actualización** (segundo `useEffect` con `[peras, manzanas]`): cada cambio en las frutas dispara un nuevo log.

**Desmontaje**: al quitar el componente de la UI, se ejecuta la limpieza del primer `useEffect`.

