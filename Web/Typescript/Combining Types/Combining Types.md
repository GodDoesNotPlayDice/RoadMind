
## Union Types
Permiten que una variable pueda ser de uno entre varios tipos diferentes. Se usa el operador `|`.

```ts
let id: string | number;
id = "ABC-123"; // válido
id = 12345;     // válido

function printAge(age: number | string) {
    console.log(`Tu edad es: ${age}`);
}
```

## Intersection Types
Combina múltiples tipos en uno solo, sumando todas sus propiedades. Se usa el operador `&`.

```ts
type Person = {
    name: string;
    age: number;
};

type Employee = {
    id: number;
    department: string;
};

type EmployeePerson = Person & Employee;

const juan: EmployeePerson = {
    name: "Juan",
    age: 30,
    id: 123,
    department: "IT"
};
```

## Type Aliases (Alias de tipos)
Crea un nuevo nombre para un tipo existente, útil para tipos complejos o repetitivos.

```ts
type UserID = string | number;
type Coordinates = {
    x: number;
    y: number;
};

function getUser(id: UserID): void {
    // ...
}

let point: Coordinates = { x: 10, y: 20 };
```

## Keyof Operator
Devuelve una unión de las claves (keys) de un tipo objeto.

```ts
type Person = {
    name: string;
    age: number;
    email: string;
};

type PersonKeys = keyof Person; // "name" | "age" | "email"

function getProperty(obj: Person, key: keyof Person) {
    return obj[key];
}
```

## Combining Types
Integración de diferentes tipos y operadores para crear estructuras complejas.

```ts
type Admin = {
    permissions: string[];
};

type User = {
    username: string;
};

type AdminUser = Admin & User;  // Intersección
type UserStatus = "active" | "inactive";  // Unión

type UserProfile = AdminUser & {
    status: UserStatus;
};

const superUser: UserProfile = {
    username: "admin",
    permissions: ["read", "write"],
    status: "active"
};
```

## Ejemplo practico

```ts
type Vehicle = {
    brand: string;
    year: number;
};

type Electric = {
    batteryCapacity: number;
};

type ElectricVehicle = Vehicle & Electric;

function printCarInfo(car: Vehicle | ElectricVehicle) {
    if ("batteryCapacity" in car) {
        console.log(`Auto eléctrico: ${car.brand}, Batería: ${car.batteryCapacity} kWh`);
    } else {
        console.log(`Auto convencional: ${car.brand}`);
    }
}
```

Sigue con [[TypeGuards and Narrowing]]
