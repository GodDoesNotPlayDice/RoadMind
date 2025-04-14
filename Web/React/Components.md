Los componentes son los bloques de construcción de las aplicaciones React. Nos permitieron dividir la interfaz de usuario en piezas independientes y reutilizables, y pensar en cada pieza de forma aislada.

## Caracteristicas de un componente

**Encapsulación**: Cada componente maneja su propia lógica y su propio estilo (en caso de que use hojas de estilo o CSS Modules). Esto facilita que trabajes en una sección específica de la interfaz sin tener que preocuparte de romper el resto de la aplicación.

**Reutilización**: Un componente puede usarse múltiples veces en diferentes lugares de la aplicación. Por ejemplo, un componente `Button` podría emplearse tanto en la cabecera como en el pie de página, con pequeñas variaciones (como color o tamaño) controladas mediante propiedades (props).

**Jerarquía**: Normalmente, una aplicación React se compone de muchos componentes organizados jerárquicamente. Por ejemplo, podrías tener un componente “Padre” (App) que contiene otros componentes “Hijos” (Header, Footer, Sidebar, etc.). A su vez, cada hijo puede contener otros componentes más pequeños.

## Tipos de componentes
En versiones anteriores de React, se hablaba mucho de **clases** y **componentes funcionales**. Hoy en día, la tendencia y recomendación es utilizar **componentes funcionales con Hooks**. Aun así, es bueno conocer ambas aproximaciones:

### Componentes de clase

```tsx
import React from 'react';

interface MiComponenteClaseProps {
  titulo: string;
}

// El estado también se puede tipar con una interfaz o type.
interface MiComponenteClaseState {
  contador: number;
}

class MiComponenteClase extends React.Component<MiComponenteClaseProps, MiComponenteClaseState> {
  constructor(props: MiComponenteClaseProps) {
    super(props);
    this.state = {
      contador: 0,
    };
  }

  render() {
    return (
      <div>
        <h1>{this.props.titulo}</h1>
        <p>Valor del contador: {this.state.contador}</p>
        <button onClick={() => this.setState({ contador: this.state.contador + 1 })}>
          Incrementar
        </button>
      </div>
    );
  }
}

export default MiComponenteClase;

```

Observa que en la declaración de la clase extendemos `React.Component<MiComponenteClaseProps, MiComponenteClaseState>` para indicar el tipo de las props y del estado.

`this.props` y `this.state` quedarán tipados automáticamente.


### Componentes funcionales
Hoy en día, la forma más común de escribir componentes en React con TypeScript es con **funciones** y **Hooks**.

```tsx
import React from 'react';

// Definimos un type o interface para las props
interface MiComponenteFuncionalProps {
  mensaje: string;
}

// React.FC (FunctionComponent) es opcional, pero útil para tipar los children y otras cosas.
const MiComponenteFuncional: React.FC<MiComponenteFuncionalProps> = ({ mensaje }) => {
  return <h2>{mensaje}</h2>;
};

export default MiComponenteFuncional;

```

- Aquí usamos `React.FC<MiComponenteFuncionalProps>` para indicar que se trata de un componente funcional y que sus props están definidas en `MiComponenteFuncionalProps`.
- Este patrón facilita que el IDE (VS Code, por ejemplo) te dé autocompletado y te muestre errores si pasas props incorrectas.

## Props
Para tipar las props, creamos una **interfaz** o un **type** que describa la forma de las propiedades que el componente espera recibir.

```ts
import React from 'react';

interface BotonProps {
  color: string;
  texto: string;
}

// Usamos React.FC para tipar el componente funcional
const Boton: React.FC<BotonProps> = ({ color, texto }) => {
  return (
    <button style={{ backgroundColor: color }}>
      {texto}
    </button>
  );
};

export default Boton;

```

En su uso:

```tsx
import React from 'react';
import Boton from './Boton';

const App: React.FC = () => {
  return (
    <div>
      <Boton color="blue" texto="Click aquí" />
      <Boton color="red" texto="Eliminar" />
    </div>
  );
};

export default App;

```

Si intentas pasarle un prop de nombre equivocado (por ejemplo, `colorr`), TypeScript te avisará que no coincide con la interfaz `BotonProps`.

## Estado (State) en componentes funcionales con Hooks
El **estado** se maneja con Hooks como `useState`, que en TypeScript también requiere tipado para la variable que almacena el estado:

```tsx
import React, { useState } from 'react';

const Contador: React.FC = () => {
  // Le decimos a useState que count es un número
  const [count, setCount] = useState<number>(0);

  return (
    <div>
      <p>Has hecho clic {count} veces</p>
      <button onClick={() => setCount(count + 1)}>
        Incrementar
      </button>
    </div>
  );
};

export default Contador;

```

`useState<number>(0)` indica que la variable `count` siempre será de tipo `number`.

Si en algún momento intentas hacer `setCount("texto")`, TypeScript marcará un error de tipo

## Ciclo de vida con `useEffect`

En lugar de los métodos de ciclo de vida (`componentDidMount`, etc.) de las clases, en componentes funcionales utilizamos `useEffect`. Con TypeScript, su uso es prácticamente igual:

```tsx
import React, { useState, useEffect } from 'react';

interface Usuario {
  id: number;
  nombre: string;
}

const ListaUsuarios: React.FC = () => {
  const [usuarios, setUsuarios] = useState<Usuario[]>([]);

  useEffect(() => {
    // Se ejecuta al montar el componente (y cada vez que cambie alguna dependencia si se declara)
    fetch('https://api.example.com/usuarios')
      .then(response => response.json())
      .then((data: Usuario[]) => setUsuarios(data));
  }, []); // con [] solo se ejecuta al montar

  return (
    <ul>
      {usuarios.map(u => (
        <li key={u.id}>{u.nombre}</li>
      ))}
    </ul>
  );
};

export default ListaUsuarios;

```

