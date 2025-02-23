El **`satisfies` keyword** es una característica más reciente en TypeScript (introducida en la versión 4.9) que permite verificar que una expresión **satisface** un tipo específico sin cambiar el tipo inferido de la expresión. Esto es útil cuando quieres asegurarte de que un valor cumple con un tipo particular, pero sin alterar la inferencia de tipos que TypeScript hace automáticamente.

```ts
type personInfo = personName | otherDetails;

type personName = "John" | "Jack" | "Justin";

type otherDetails = {
    id: number;
    age: number;
};

type Person = {
    myInfo: personInfo;
    myOtherInfo: personInfo;
};

const applicant = {
    myInfo: "John",
    myOtherInfo: { id: 123, age: 22 },
} satisfies Person;

// TypeScript sabe que applicant.myInfo es de tipo personName
console.log(applicant.myInfo); // "John"

// TypeScript sabe que applicant.myOtherInfo es de tipo otherDetails
console.log(applicant.myOtherInfo.id); // 123
console.log(applicant.myOtherInfo.age); // 22
```

- **`personInfo`**: Es un tipo unión que puede ser un nombre (`personName`) o detalles adicionales (`otherDetails`).
- **`Person`**: Define la estructura de un objeto con dos propiedades de tipo `personInfo`.
- **`applicant`**: Es un objeto que cumple con la estructura de `Person` y utiliza `satisfies` para asegurar que cumple con el tipo `Person` sin cambiar la inferencia de tipos


