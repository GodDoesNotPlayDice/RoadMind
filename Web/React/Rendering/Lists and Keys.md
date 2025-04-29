# Keys
Un `key` es simplemente un **string** o **número** que identifica de forma única cada elemento en una lista de React

Piensa en ellas como etiquetas adhesivas con el nombre de cada fruta (peras, manzanas…) que pegas en tu canasta: así no importa cómo mezcles las frutas, siempre sabrás cuál es cuál.

## Porque son importantes?
**Mantener el orden**: si mueves, insertas o eliminas elementos, React utiliza el `key` para alinear correctamente los componentes antiguos con los nuevos.
**Preservar estado**: si un `<input>` o componente hijo guarda su propio estado local, un `key` estable evita que React lo destruya y recree por accidente.
**Eficiencia**: React compara las keys entre renders y solo actualiza los nodos necesarios, en lugar de rehacer toda la lista.

## ¿Como elegir una buena key
**Datos únicos**: si vienen de una base de datos, usa su ID natural.
**IDs locales**: en apps que crean datos en el navegador, genera IDs con `crypto.randomUUID()` o librerías como `uuid`.
**Evitar índices**: usar el índice de array (`map((item, i) => key={i})`) falla cuando insertas o borras en medio, porque las posiciones cambian.
**Nunca generarlos en el render**: `key={Math.random()}` produce un nuevo valor cada vez, haciendo que React recree todo.


## Reglas de las keys
Deben ser **únicas entre hermanos** (en la misma lista).
Pueden repetirse en **listas distintas** (diferentes arrays).
Deben ser **estables**: solo cambian si el item realmente cambia de identidad.

_React no pasa el prop `key` al componente hijo; lo usa internamente. Si tu componente necesita el mismo valor, pásalo como otro prop (por ejemplo `userId={id}`)._


```tsx
interface Fruta {
  id: string;
  nombre: string;
}

const cesta: Fruta[] = [
  { id: 'p1', nombre: '🍐 Pera' },
  { id: 'm1', nombre: '🍎 Manzana' },
  { id: 'p2', nombre: '🍐 Pera' },
];

// Al renderizar:
<ul>
  {cesta.map(fruta => (
    // Cada <li> tiene su etiqueta (key) única:
    <li key={fruta.id}>
      {fruta.nombre}
    </li>
  ))}
</ul>
```

Aquí `p1`, `m1`, `p2` son nuestras “etiquetas” en la canasta. Si intercambias una pera por una manzana nueva, React sabrá exactamente cuál cambió gracias al `key`.

## Errores comunes
**Usar índices**: genera bugs sutiles al insertar o borrar elementos.
**Math.random()**: rompe la correspondencia entre renders y destruye el estado de los hijos.
**Keys cambiantes**: si una key cambia arbitrariamente, React no puede detectar qué elemento es el mismo y re-renderiza todo


`<li key={fruta.nombre}>{fruta.nombre}</li>`
![[Pasted image 20250428135436.png]]

`<li>{fruta.nombre}</li>`
![[Pasted image 20250428135542.png]]

