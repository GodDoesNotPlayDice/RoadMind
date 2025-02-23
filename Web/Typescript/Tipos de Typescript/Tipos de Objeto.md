Los tipos de objetos son fundamentales para definir estructuras de datos más complejas.

## Interface
Las interfaces en TypeScript son una forma poderosa de definir contratos dentro de tu código. 

Permiten especificar la forma que debe tener un objeto, incluyendo los tipos de sus propiedades y métodos.

```ts
interface Person {
    name: string;
    age: number;
    greet(): void;
}

let user: Person = {
    name: "Alice",
    age: 25,
    greet() {
        console.log("Hello, " + this.name);
    }
};
```
## Class
Las clases en TypeScript son una forma de crear objetos con propiedades y métodos. 

TypeScript añade tipos y modificadores de acceso a las clases de JavaScript.

```ts
class Animal {
    name: string;
    constructor(theName: string) {
        this.name = theName;
    }
    move(distanceInMeters: number = 0) {
        console.log(`${this.name} moved ${distanceInMeters}m.`);
    }
}

let dog = new Animal("Rover");
dog.move(10);
```
## Enum
Los enums permiten definir un conjunto de constantes con nombre. Pueden ser numéricos o basados en cadenas.

```ts
enum Direction {
    Up = 1,
    Down,
    Left,
    Right
}

let dir: Direction = Direction.Up;
```
## Array
Los arrays en TypeScript pueden contener elementos de un tipo específico. Puedes definir arrays de varias maneras.

```ts
let list: number[] = [1, 2, 3];
let list2: Array<number> = [1, 2, 3]; // Usando genéricos
```
## Tuple
Las tuplas permiten expresar un array con un número fijo de elementos cuyos tipos son conocidos, pero no necesariamente iguales.

```ts
let x: [string, number];
x = ["hello", 10]; // OK
// x = [10, "hello"]; // Error
```

## Object
El tipo `object` representa cualquier valor que no sea un tipo primitivo (es decir, cualquier cosa que no sea `number`, `string`, `boolean`, `symbol`, `null`, o `undefined`).

```ts
let obj: object = { name: "Alice" };
```

