TypeScript es un lenguaje de programación de código abierto desarrollado y mantenido por Microsoft. Es un superconjunto de JavaScript, lo que significa que cualquier código válido en JavaScript también es válido en TypeScript. 

Sin embargo, TypeScript añade características adicionales que no están presentes en JavaScript.

## Características principales de TypeScript:

**Tipado estático**: TypeScript introduce un sistema de tipos estáticos, lo que permite a los desarrolladores definir tipos para variables, parámetros de funciones, valores de retorno, etc. Esto ayuda a detectar errores en tiempo de compilación, antes de que el código se ejecute.

**Interfaces y tipos personalizados**: TypeScript permite definir interfaces y tipos personalizados, lo que facilita la creación de estructuras de datos complejas y asegura que los objetos sigan un formato específico.

**Compatibilidad con JavaScript**: Dado que TypeScript es un superconjunto de JavaScript, puedes integrarlo gradualmente en proyectos existentes. Puedes mezclar código TypeScript y JavaScript en el mismo proyecto.

**Herramientas de desarrollo avanzadas**: TypeScript ofrece un mejor soporte para herramientas de desarrollo como **autocompletado**, **refactorización** y **detección de errores en tiempo real**, lo que mejora la productividad.

**Decoradores**: TypeScript soporta decoradores, que son una característica experimental de JavaScript que permite modificar o extender clases, métodos, propiedades, etc.

**Compilación a JavaScript**: TypeScript se compila a JavaScript, lo que significa que el código TypeScript se transforma en código JavaScript que puede ser ejecutado en cualquier navegador o entorno que soporte JavaScript.


## Ejemplo básico

```js
// Definición de una interfaz
interface Persona {
    nombre: string;
    edad: number;
}

// Función que utiliza la interfaz
function saludar(persona: Persona): string {
    return `Hola, ${persona.nombre}! Tienes ${persona.edad} años.`;
}

// Objeto que cumple con la interfaz
const usuario: Persona = { nombre: "Juan", edad: 30 };

// Llamada a la función
console.log(saludar(usuario)); // Salida: Hola, Juan! Tienes 30 años.
```

## Ventajas de usarlo

**Detección temprana de errores**: Al tener un sistema de tipos estáticos, muchos errores se detectan en tiempo de compilación, lo que reduce los errores en tiempo de ejecución.

**Mejor mantenibilidad**: El código es más fácil de entender y mantener, especialmente en proyectos grandes.

**Mayor productividad**: Las herramientas de desarrollo mejoradas, como el autocompletado y la refactorización, hacen que los desarrolladores sean más eficientes.

**Comunidad y soporte**: TypeScript tiene una gran comunidad y está respaldado por Microsoft, lo que garantiza un soporte continuo y actualizaciones frecuentes.


A continuación los tipos [[Primitivos]], [[Tipos de Objeto]], [[Top Types y Bottom Types]] y las acertaciones de tipo [[Aserciones de Tipo]]

## Acerca de la instalación
Para comenzar a usar TypeScript, necesitas tener Node.js instalado. Luego, puedes instalar TypeScript globalmente usando **npm**:

```bash
npm install -g typescript
```

Una vez instalado, puedes compilar archivos TypeScript (`.ts`) a JavaScript (`.js`) usando el comando `tsc`:

```
tsc archivo.ts
```

Esto generará un archivo `archivo.js` que puedes ejecutar en cualquier entorno JavaScript.

Typescript es posible de configurar en un archivo llamado 