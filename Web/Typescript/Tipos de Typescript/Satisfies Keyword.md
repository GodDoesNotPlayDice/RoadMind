El **`satisfies` keyword** es una característica más reciente en TypeScript (introducida en la versión 4.9) que permite verificar que una expresión **satisface** un tipo específico sin cambiar el tipo inferido de la expresión. Esto es útil cuando quieres asegurarte de que un valor cumple con un tipo particular, pero sin alterar la inferencia de tipos que TypeScript hace automáticamente.

```ts
type Person = {
    name: string;
    age: number;
};

const user = {
    name: "Alice",
    age: 25,
    location: "Wonderland"
} satisfies Person;

// TypeScript sabe que user tiene las propiedades name y age, pero también permite la propiedad location
console.log(user.name); // "Alice"
console.log(user.age); // 25
console.log(user.location); // "Wonderland"
```

En este ejemplo, `user` satisface el tipo `Person`, pero TypeScript también permite que `user` tenga propiedades adicionales como `location`. Esto es diferente de una aserción de tipo (`as`), que cambiaría el tipo inferido de `user`.


