En TypeScript, la compatibilidad de tipos no se basa en los nombres de los tipos, sino en su estructura.

Esto significa que dos tipos son compatibles si tienen la misma forma o estructura, incluso si tienen nombres diferentes.

```ts
interface Point {
    x: number;
    y: number;
}

let p1: Point = { x: 10, y: 20 };
let p2: { x: number; y: number } = p1;

console.log(p2.x); // Output: 10
```

### En este ejemplo:
- `p1` es de tipo `Point`, que es una interfaz con dos propiedades: `x` y `y`, ambas de tipo `number`.
- `p2` es de tipo `{ x: number; y: number }`, que es un tipo anónimo con la misma estructura que `Point`.

Aunque `p1` y `p2` tienen tipos con nombres diferentes (`Point` vs. `{ x: number; y: number }`), TypeScript los considera compatibles porque tienen la misma estructura. Por eso puedes asignar `p1` a `p2` sin problemas.

## ¿Por qué es util?
Este enfoque de tipado estructural es útil porque permite mayor flexibilidad en el código. No necesitas que los tipos tengan el mismo nombre para que sean compatibles, siempre y cuando tengan la misma forma. Esto facilita la reutilización de código y la interoperabilidad entre diferentes partes de tu programa.

