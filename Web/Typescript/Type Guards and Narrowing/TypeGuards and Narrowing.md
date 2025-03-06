Técnicas para reducir el tipo de una variable dentro de un bloque de código, asegurando seguridad de tipos.

## typeof
Técnicas para reducir el tipo de una variable dentro de un bloque de código, asegurando seguridad de tipos.

```ts
function printValue(value: string | number) {
    if (typeof value === "string") {
        console.log(value.toUpperCase()); // TypeScript sabe que es string
    } else {
        console.log(value.toFixed(2));    // TypeScript sabe que es number
    }
}
```

## instanceof
Comprueba si un objeto es instancia de una clase específica.

```ts
class Car {
    drive() {
        console.log("Driving...");
    }
}

class Bike {
    pedal() {
        console.log("Pedaling...");
    }
}

function useVehicle(vehicle: Car | Bike) {
    if (vehicle instanceof Car) {
        vehicle.drive(); // TypeScript sabe que es un Car
    } else {
        vehicle.pedal();  // TypeScript sabe que es un Bike
    }
}
```

## Equality
Usa comparaciones estrictas (`===` o `!==`) para discriminar tipos.

```ts
function formatValue(value: string | null) {
    if (value === null) {
        return "Valor nulo";
    }
    return value.trim(); // TypeScript sabe que es string
}
```

## Truthiness
Evalúa si un valor es `truthy` o `falsy` para estrechar tipos.

```ts
function printLength(str?: string) {
    if (str) {                  // Filtra undefined y strings vacíos
        console.log(str.length);
    } else {
        console.log("No hay string");
    }
}
```

## Type Predicates (Predicados de tipo)
Funciones personalizadas que devuelven un booleano y ayudan a TypeScript a inferir tipos.

```ts
type Fish = { swim: () => void };
type Bird = { fly: () => void };

function isFish(pet: Fish | Bird): pet is Fish { // Predicado de tipo
    return "swim" in pet;
}

function move(pet: Fish | Bird) {
    if (isFish(pet)) {
        pet.swim(); // TypeScript sabe que es Fish
    } else {
        pet.fly();  // TypeScript sabe que es Bird
    }
}
```


## Ejemplo combinado
**Narrowing (estrechamiento de tipos)**:
- Reduce el tipo de `entity` de `User | Admin | null` a `User | Admin` (elimina `null`)
- Luego, reduce `User | Admin` a `User` o `Admin` usando el predicado `isAdmin`.
**Seguridad de tipos**:
- TypeScript garantiza que no se acceda a propiedades incorrectas (por ejemplo, `permissions` en un `User` o `name` en un `Admin`).

```ts
type User = { name: string; age: number };
type Admin = { permissions: string[] };

function isAdmin(user: User | Admin): user is Admin {
    return "permissions" in user;
}

function logDetails(entity: User | Admin | null) {
    if (!entity) {
        console.log("Entidad no definida");
        return;
    }

    if (typeof entity === "object") {
        if (isAdmin(entity)) {
            console.log("Permisos:", entity.permissions); // Admin
        } else {
            console.log("Nombre:", entity.name); // User
        }
    }
}

const user: User = { name: "Juan", age: 30 };
const admin: Admin = { permissions: ["read", "write"] };

logDetails(user);   // Salida: "Nombre: Juan"
logDetails(admin);  // Salida: "Permisos: ['read', 'write']"
logDetails(null);   // Salida: "Entidad no definida"

```

### Explicación
1. **`User`**: Representa un usuario con dos propiedades:
    - `name`: Un string que almacena el nombre del usuario.
    - `age`: Un número que almacena la edad del usuario.
2. **`Admin`**: Representa un administrador con una propiedad:
    - `permissions`: Un array de strings que almacena los permisos del administrador.

```ts
type User = { name: string; age: number };
type Admin = { permissions: string[] };
```

#### Función `isAdmin`
Es un **type predicate** (predicado de tipo) que verifica si un objeto es de tipo `Admin`.

- **Parámetro**: `user` de tipo `User | Admin`.
- **Retorno**: `user is Admin` (un booleano que indica si `user` es de tipo `Admin`).
- **Lógica**: Usa el operador `in` para verificar si la propiedad `permissions` existe en el objeto `user`.

```ts
function isAdmin(user: User | Admin): user is Admin {
    return "permissions" in user;
}
```

#### Función `logDetails`
Esta función toma un parámetro `entity` que puede ser de tipo `User`, `Admin` o `null`, y realiza lo siguiente:
1. **Verifica si `entity` es `null`**:
    - Si es `null`, imprime "Entidad no definida" y termina la ejecución.
2. **Verifica si `entity` es un objeto**:
    - Usa `typeof entity === "object"` para asegurarse de que `entity` no es `null` ni un tipo primitivo.
3. **Usa el predicado `isAdmin`**:
    - Si `isAdmin(entity)` devuelve `true`, TypeScript infiere que `entity` es de tipo `Admin` y accede a `entity.permissions`.
        
    - Si `isAdmin(entity)` devuelve `false`, TypeScript infiere que `entity` es de tipo `User` y accede a `entity.name`.

```ts
function logDetails(entity: User | Admin | null) {
    if (!entity) {
        console.log("Entidad no definida");
        return;
    }

    if (typeof entity === "object") {
        if (isAdmin(entity)) {
            console.log("Permisos:", entity.permissions); // Admin
        } else {
            console.log("Nombre:", entity.name); // User
        }
    }
}
```


## Por qué son importantes
- **Seguridad de tipos**: Evitan errores en tiempo de ejecución.
- **Autocompletado**: Habilitan sugerencias específicas del tipo en editores.
- **Flexibilidad**: Permiten trabajar con uniones complejas de manera segura.


Continua con [[Funciones en Typescript]]
