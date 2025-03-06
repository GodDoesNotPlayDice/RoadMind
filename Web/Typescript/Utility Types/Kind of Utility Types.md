Son tipos predefinidos que te permiten manipular y transformar otros tipos de manera más eficiente.

Estos tipos son útiles para crear nuevos tipos basados en tipos existentes, lo que puede ahorrar tiempo y reducir la complejidad en tu código.

## `Partial <T>`
Crea un tipo con todas las propiedades de `T` establecidas como opcionales.

Esto es útil cuando necesita crear un objeto con solo un subconjunto de las propiedades de un tipo existente.

```ts
interface User {
    id: number;
    name: string;
    age: number;
}

type PartialUser = Partial<User>;

const user: PartialUser = {
    name: "John"
};
// `id` y `age` son opcionales en `PartialUser`
```

## `Pick<T, K>`
Crea un tipo seleccionando un conjunto de propiedades `K` de `T`. Es útil cuando solo necesitas un subconjunto de propiedades de un tipo.

```ts
interface User {
    id: number;
    name: string;
    age: number;
}

type UserName = Pick<User, 'name'>;

const userName: UserName = {
    name: "John"
};
// Solo `name` está presente en `UserName`
```

## `Omit<T, K>`
Crea un tipo omitiendo un conjunto de propiedades `K` de `T`. Es lo opuesto a `Pick`.

```ts
interface User {
    id: number;
    name: string;
    age: number;
}

type UserWithoutAge = Omit<User, 'age'>;

const userWithoutAge: UserWithoutAge = {
    id: 1,
    name: "John"
};
// `age` no está presente en `UserWithoutAge`
```

## `Readonly<T>`
Crea un tipo con todas las propiedades de `T` como de solo lectura. Esto significa que no se pueden modificar después de su creación

```ts
interface User {
    id: number;
    name: string;
}

type ReadonlyUser = Readonly<User>;

const user: ReadonlyUser = {
    id: 1,
    name: "John"
};

// user.name = "Jane"; // Error: No se puede asignar a 'name' porque es de solo lectura
```


## `Record<K, T>`
rea un tipo con un conjunto de propiedades `K` donde cada propiedad es del tipo `T`. Útil para crear objetos con claves dinámicas.

```ts
type UserRoles = Record<string, string>;

const roles: UserRoles = {
    admin: "Admin",
    user: "User"
};
// `roles` es un objeto con claves dinámicas y valores de tipo `string`
```

## `Exclude<T, U>`
Crea un tipo excluyendo de `T` todos los tipos que son asignables a `U`.

```ts
type T = string | number | boolean;
type U = string | boolean;

type Result = Exclude<T, U>; // Result es `number`
```

## `Extract<T, U>`
Crea un tipo extrayendo de `T` todos los tipos que son asignables a `U`.

```ts
type T = string | number | boolean;
type U = string | boolean;

type Result = Extract<T, U>; // Result es `string | boolean`
```

## `Awaited<T>`
Crea un tipo que representa el tipo resuelto de una promesa `T`.

```ts
type PromiseType = Promise<string>;
type ResolvedType = Awaited<PromiseType>; // ResolvedType es `string`
```

## `Parameters<T>`
Crea un tipo que es una tupla de los tipos de los parámetros de una función `T`.

```ts
function greet(name: string, age: number) {
    console.log(`Hello ${name}, you are ${age} years old.`);
}

type GreetParams = Parameters<typeof greet>; // GreetParams es [string, number]
```

## `NonNulleable<T>`
Crea un tipo excluyendo `null` y `undefined` de `T`.

```ts
type T = string | number | null | undefined;
type NonNullableT = NonNullable<T>; // NonNullableT es `string | number`
```

## `ReturnType<T>`
Crea un tipo que es el tipo de retorno de una función `T`.

```ts
function greet(): string {
    return "Hello, World!";
}

type GreetReturnType = ReturnType<typeof greet>; // GreetReturnType es `string`
```

## `InstanceType<T>`
Crea un tipo que es el tipo de instancia de un constructor `T`.

```ts
class User {
    constructor(public name: string) {}
}

type UserInstance = InstanceType<typeof User>; // UserInstance es `User`

const user: UserInstance = new User("John");
```

Mas avanzado en [[Advanced Types]] o con los [[Módulos de Typescript]]
