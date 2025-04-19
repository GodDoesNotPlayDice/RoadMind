Un **Effect** en React tiene un ciclo de vida independiente del componente: en lugar de “montar–actualizar–desmontar”, cada Effect solo sabe cómo **iniciar** y **detener** la sincronización con sistemas externos según cambien sus dependencias.

El **cuerpo** del Effect describe cómo arrancar la sincronización, y la **función de limpieza** (`cleanup`) cómo detenerla. Cada vez que alguno de los valores declarados en el array de dependencias cambia, React **re-sincroniza** el Effect: primero llama al cleanup anterior y luego ejecuta de nuevo el cuerpo con los valores actualizados.

[Ciclo de vida de los efectos reactivos](https://react.dev/learn/lifecycle-of-reactive-effects)
[Video explicativo](https://www.youtube.com/watch?v=kKVVan3EGoU)
# Fases del Ciclo

## Inicio y limpieza
Cuando el componente se monta o alguna dependencia cambia, React **ejecuta** el cuerpo del **Effect** para iniciar la **sincronización** (por ejemplo, abrir una conexión)

Cuando el Effect necesita detenerse (por cambio de dependencia o desmontaje), React **invoca** la función de limpieza que retornaste para parar la sincronización (por ejemplo, cerrar la conexión)

A diferencia del ciclo de vida de un componente, este proceso puede repetirse **múltiples veces** sin desmontar el componente
## Re sync
Tras una re-renderización, React **compara** cada valor en el array de dependencias con su valor anterior usando `Object.is` para decidir si debe volver a sincronizar

Si detecta una diferencia, primero llama al **cleanup previo** y luego ejecuta el efecto con los nuevos valores

En modo desarrollo, React fuerza un montaje y limpieza **extra** para verificar que tu cleanup funciona correctamente


# Dependencia y valores reactivos

## ¿Que valores son “reactivos”?
**Props**, **state** y **variables definidas en el cuerpo del componente** son reactivos porque pueden cambiar en cada render

Cualquier valor que deriven de **props** o **state** también es reactivo y debe incluirse en el array de dependencias

## Dependencias vacías
Un array de dependencias `[]` indica que tu Effect no lee valores reactivos, por lo que solo corre al **montar** y su cleanup solo al **desmontar**

Si más tarde conviertes alguna dependencia en reactiva, bastará con **añadirla** al array sin cambiar el cuerpo del Effect


`ContadorFrutas.tsx`
```tsx
import React, { useState, useEffect } from "react";

export type Fruta = "manzanas" | "peras";

export const ContadorFrutas: React.FC<{ fruta: Fruta }> = ({ fruta }) => {
  const [cantidad, setCantidad] = useState(0);

  useEffect(() => {
    // → INICIO: cuando montamos o cambia la fruta
    console.log(`🌱 Empezamos a contar ${fruta}`);
    const intervalo = setInterval(() => {
      setCantidad((c) => c + 1); // llega 1 fruta cada segundo
    }, 1000);

    // → LIMPIEZA: antes de cambiar de fruta o al desmontar
    return () => {
      clearInterval(intervalo);

      console.log(`🛑 Dejamos de contar ${fruta}`);
    };
  }, [fruta]); // ← depende de “fruta”

  return (
    <p>
      Has recogido {cantidad} {fruta}
    </p>
  );
};

```


`App.tsx`
```tsx
import { ContadorFrutas, Fruta } from "./ContadorFrutas";
import { useState } from "react";

function App() {
  const [fruta, setFruta] = useState<Fruta>("manzanas");
  return (
    <>
      <div>
        <h1>Recolector de Frutas</h1>

        <button onClick={() => setFruta("manzanas")}>Manzanas</button>

        <button onClick={() => setFruta("peras")}>Peras</button>

        <ContadorFrutas fruta={fruta} />
      </div>
    </>
  );
}

export default App;

```

