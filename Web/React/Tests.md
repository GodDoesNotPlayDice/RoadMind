## Indicé

1) Primeras pruebas
2) Jest
3) Expect
4) toBe
5) Commands
6) Re-ver componentes
7) Simular Eventos.

## Que son las pruebas?

Las pruebas no son una perdida de tiempo, son muy importantes ya que nos da la seguridad que la aplicación va a funcionar como corresponde, existen dos tipos de prueba

**Pruebas Unitarias:** Enfocadas en pequeñas piezas de funcionalidades.
**Pruebas de Integración:** Enfocadas en como reaccionan varias piezas en conjunto.

**Características**: Fáciles de escribir, leer, confiables, rápidas y unitarias.

### AAA
AAA viene de Arrange, Act, Assert, definiendo los pasos seria.

1) Arrange: Es el paso inicial, donde inicializaremos variables e importaciones necesarias.
2) Act: Donde le asignamos estímulos al sujeto ósea llamar métodos, simular clicks, etc. 
3) Assert: Observar el comportamiento resultante, que pase algo o no pase.





## Jest
Jest is a delightful JavaScript Testing Framework with a focus on simplicity.

Oficial Sito :  https://jestjs.io/

Inicialización.

```bash
npm i --save-dev jest
```

```json
  "scripts": {
    "test": "jest --watchAll"
  }
```

Luego crear un folder llamado `tests` donde el archivo debe ser nombre.test.js o ts.

```js
test("Prueba bien buena", () => { // Forma inicial de los test
    // 1. Arrange (preparar)
    const mensaje = "Hola Mundo";
    // 2. Act (actuar)
    const mensaje2 = mensaje.trim();
    // 3. Assert (afirmar)
    expect(mensaje).toBe(mensaje2); // Comparar variables.
});
```

Para obtener el snipet pueden usar

```bash
npm i --save-dev @types/jest
```

Se pueden agrupar en una descripción.
```js
describe('Grupo de prueba', () => {
    test("Prueba bien buena", () => {
        // 1. Arrange (preparar)
        const mensaje = "Hola Mundo";
        // 2. Act (actuar)
        const mensaje2 = mensaje.trim();
        // 3. Assert (afirmar)
        expect(mensaje).toBe(mensaje2);
    });
});
```






