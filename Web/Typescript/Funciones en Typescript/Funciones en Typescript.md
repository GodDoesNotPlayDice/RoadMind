L.as funciones se pueden definir de manera similar a JavaScript, pero con la ventaja de poder especificar tipos para los parámetros y el valor de retorno.

```ts
function add(a: number, b: number): number {
    return a + b;
}

console.log(add(2, 3)); // 5
```

## Tipado de funciones
TypeScript permite especificar los tipos de los parámetros y el tipo de retorno de una función. Esto ayuda a evitar errores y mejora la legibilidad del código.

```ts
function greet(name: string): string {
    return `Hello, ${name}`;
}

console.log(greet("Alice")); // Hello, Alice
```

## Sobrecarga de funciones
La sobrecarga de funciones permite definir múltiples firmas para una misma función, lo que permite que la función maneje diferentes tipos de parámetros.

```ts
function combine(a: string, b: string): string;
function combine(a: number, b: number): number;
function combine(a: any, b: any): any {
    return a + b;
}

console.log(combine("Hello, ", "World")); // Hello, World
console.log(combine(1, 2)); // 3
```

