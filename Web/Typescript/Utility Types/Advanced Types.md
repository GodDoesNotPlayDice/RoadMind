## Mapped Types
Los **Mapped Types** te permiten crear nuevos tipos basados en las propiedades de un tipo existente. Puedes transformar las propiedades de un tipo de manera sistemática.

```ts
interface Person {
    name: string;
    age: number;
}

// Hacer todas las propiedades opcionales
type PartialPerson = { [K in keyof Person]?: Person[K] };
// PartialPerson es { name?: string; age?: number; }

// Hacer todas las propiedades de solo lectura
type ReadonlyPerson = { readonly [K in keyof Person]: Person[K] };
// ReadonlyPerson es { readonly name: string; readonly age: number; }
```

## Conditional Types
Los **Conditional Types** te permiten definir tipos que dependen de una condición. Son similares a los operadores ternarios en JavaScript.

```ts
type IsString<T> = T extends string ? true : false;

type A = IsString<string>; // A es true
type B = IsString<number>; // B es false
```

Un uso común es con `infer`, que permite extraer tipos dentro de una condición:

```ts
type ReturnType<T> = T extends (...args: any[]) => infer R ? R : never;

function foo(): number {
    return 42;
}

type FooReturn = ReturnType<typeof foo>; // FooReturn es number
```

## Literal Types
Los **Literal Types** son tipos que representan un valor específico. Pueden ser strings, números o booleanos.

```ts
type Direction = "north" | "south" | "east" | "west";

let dir: Direction;
dir = "north"; // Válido
dir = "up"; // Error: "up" no es un valor válido para Direction
```

## Template Literal Types
Los **Template Literal Types** te permiten crear tipos basados en cadenas de texto, similar a cómo funcionan los template literals en JavaScript.

```ts
type EventName = "click" | "scroll";
type EventHandler = `on${Capitalize<EventName>}`;

let handler: EventHandler;
handler = "onClick"; // Válido
handler = "onScroll"; // Válido
handler = "onHover"; // Error: "onHover" no es un valor válido para EventHandler
```

## Recursive Types
Los **Recursive Types** son tipos que se refieren a sí mismos. Son útiles para definir estructuras de datos recursivas como árboles o listas enlazadas.

```ts
interface TreeNode<T> {
    value: T;
    left?: TreeNode<T>;
    right?: TreeNode<T>;
}

let tree: TreeNode<number> = {
    value: 1,
    left: {
        value: 2,
        left: { value: 4 },
        right: { value: 5 }
    },
    right: {
        value: 3
    }
};
```

Continua con los Módulos [[Módulos de Typescript]]