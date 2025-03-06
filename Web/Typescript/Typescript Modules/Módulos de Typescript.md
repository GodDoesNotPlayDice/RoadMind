Los módulos en TypeScript son una forma de organizar y encapsular el código. Pueden ser archivos individuales que exportan e importan funcionalidades. Por ejemplo:

```ts
// modulo.ts
export class MiClase {
    // ...
}

// otroArchivo.ts
import { MiClase } from './modulo';
const instancia = new MiClase();
```

## Namespace
En TypeScript, los namespaces son una forma de organizar el código en contenedores lógicos. Esto es útil para evitar colisiones de nombres en el ámbito global. Por ejemplo:

```ts
namespace MiNamespace {
    export class MiClase {
        // ...
    }
}

const instancia = new MiNamespace.MiClase();
```

## Ambient Modules
Los módulos ambientales se utilizan para describir el tipo de bibliotecas externas que no están escritas en TypeScript. Se declaran en archivos `.d.ts`. Por ejemplo:

```ts
declare module "nombre-del-modulo" {
    export function algunaFuncion(): void;
}
```

## External Modules
Los módulos externos son una forma de organizar el código en archivos separados que pueden ser importados y exportados. TypeScript soporta módulos CommonJS y ES6. Por ejemplo:

```ts
// archivo1.ts
export function funcion1() {
    // ...
}

// archivo2.ts
import { funcion1 } from './archivo1';
funcion1();
```

## Namespace Augmentation
La ampliación de namespaces permite agregar nuevas definiciones a un namespace existente. Esto es útil para extender bibliotecas de terceros. Por ejemplo:

```ts
namespace MiNamespace {
    export function nuevaFuncion() {
        // ...
    }
}
```


## Global Augmentation
La ampliación global permite agregar definiciones al ámbito global. Esto puede ser útil para extender tipos globales. Por ejemplo:

```ts
declare global {
    interface Window {
      nuevaPropiedad: any;
    }
}
```


