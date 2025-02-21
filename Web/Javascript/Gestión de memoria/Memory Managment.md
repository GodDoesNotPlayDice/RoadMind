Es cómo JavaScript **asigna, usa y libera memoria** automáticamente para que tú no tengas que hacerlo manualmente (a diferencia de lenguajes como C o C++).

**¿Por qué importa?**  
Si la memoria no se gestiona bien, tu aplicación puede volverse lenta, consumir muchos recursos o incluso crashearse.

**Ejemplo:**  
Cuando creas un objeto o una variable, JavaScript reserva memoria para guardarlo. Cuando dejas de usarlo, JavaScript lo elimina por ti (¡pero a veces puede fallar si hay errores en tu código!).

## Memory Lifecycle (Ciclo de vida de la memoria)
Son las **tres etapas** por las que pasa la memoria en cualquier programa:

### Asignación (Allocation):
JavaScript reserva memoria cuando declaras variables, objetos, arrays, etc.

```js
let nombre = "Ana"; // Asigna memoria para un string.
const lista = [1, 2, 3]; // Asigna memoria para un array.
```

### Uso (Usage):
Cuando lees o modificas esos datos.

```js
console.log(nombre); // Usa la memoria asignada.
lista.push(4); // Modifica la memoria del array.
```

### Liberación (Release)
Cuando la memoria ya no se necesita, JavaScript la libera mediante el **Garbage Collector**.

## Garbage Collection (Recolección de basura)
Es el proceso automático de JavaScript para **limpiar la memoria que ya no se usa**.

### ¿Cómo funciona?  
El Garbage Collector identifica qué datos ya no son accesibles desde tu código (por ejemplo, variables fuera de alcance o objetos sin referencias).

```js
function ejemplo() {
  let temporal = { dato: "hola" }; // Asigna memoria.
} // Al terminar la función, "temporal" ya no es accesible. ¡Se libera su memoria!
```

#### Algoritmo clave:  
Usa el **Mark and Sweep** ("marcar y barrer"):
    1. **Marca** todos los objetos accesibles desde el código.        
    2. **Barré** (elimina) los no marcados.


## Errores comunes que causan fugas de memoria
- **Evita retener referencias innecesarias** (objetos grandes, variables globales).
- Usa herramientas como el **Chrome DevTools Memory Tab** para detectar fugas.

**Variables globales:** Ocupan memoria durante toda la ejecución.
```js
function crearDato() {
  datoGlobal = "Esto nunca se borrará"; // ¡Variable global implícita!
}
```

**Event Listeners olvidados:** Si no los remueves, siguen en memoria.
```js
button.addEventListener("click", onClick); // Si el botón se elimina, el listener sigue ahí.
// Solución: Usar removeEventListener() cuando ya no se necesite.
```

**Closures que retienen referencias:**
```js
function outer() {
  const grande = new Array(1000000); // Objeto grande en memoria.
  return function inner() {
    // ¡"inner" retiene acceso a "grande" aunque no se use!
  };
}
```


