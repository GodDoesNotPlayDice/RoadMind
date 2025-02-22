El archivo **`tsconfig.json`** en TypeScript sirve para configurar cómo el compilador (tsc) debe comportarse al transformar tu código TypeScript a JavaScript. Te permite indicar qué versión de JavaScript quieres generar, dónde quieres guardar los archivos resultantes, qué directorios incluir o excluir de la compilación, entre otras muchas opciones.

## Por qué es importante el tsconfig.json?

**Centraliza la configuración**: te evita tener que pasar banderas y parámetros al compilador cada vez que compilas.

**Controla el entorno de compilación**: escoger el `target`, el sistema de módulos, las reglas de tipado, etc.

**Organiza tu proyecto**: separar el código fuente (`src`) de la salida (`dist`) facilita la limpieza y la estructura.

**Personalización avanzada**: hay muchas otras opciones que puedes agregar (por ejemplo, `noImplicitAny`, `strictNullChecks`, `esModuleInterop`, `sourceMap`, etc.) para adaptar el proceso de compilación a tus necesidades.

```json
{
  "compilerOptions": {
    "target": "es5",
    "module": "commonjs",
    "strict": true,
    "outDir": "./dist",
    "rootDir": "./src"
  },
  "exclude": ["node_modules"],
  "include": ["src"]
}
```

## `compilerOptions`

### target: `es5`
- Indica la versión de Javascript a la que se va compilar el código TypeScript.
- `"es5"` es una versión antigua pero muy compatible con navegadores y entornos más viejos.
- Puedes usar otras opciones como `"es6"`, `"es2017"`, `"es2020"`, `"esnext"`, etc., dependiendo de la compatibilidad que necesites.

### module: `commonjs`
- Define el sistema de módulos que se utilizará en el JavaScript resultante.
- `commonjs` es el formato estándar en Node.js, pero hay otras opciones como `esnext`, `amd`, `umd`, etc
- Escoger `commonjs` facilita usar `require` y `module.exports`, aunque en proyectos modernos a veces se opta por `esnext` para usar `import/export`

### strict: `true`
- Activa el modo estricto de TypeScript, que incluye varias comprobaciones más rigurosas (por ejemplo, `strictNullChecks`, `noImplicitAny`, etc.).
- Ayuda a detectar errores potenciales antes de que se ejecuten, haciendo el código más seguro y fiable.
- Se recomienda mantener esta opción en `true` para aprovechar las ventajas de TypeScript.

### outDir: `"./dist"`
- Especifica la carpeta donde se guardarán los archivos JavaScript resultantes después de compilar.
- Por ejemplo, si tienes un archivo `src/index.ts`, tras compilarlo se guardará como `dist/index.js`.
- Esto te ayuda a separar el código fuente (TypeScript) de la salida compilada (JavaScript).

### rootDir: `"./src"`
- Indica la carpeta raíz de tu código TypeScript.
- El compilador usará esta ruta para organizar la estructura de carpetas dentro de `outDir`.
- Básicamente, le estás diciendo: “todos mis archivos .ts están dentro de `src`, y quiero que mantengas la misma estructura al generar los archivos en `dist`”.

## `exclude`

### `"exclude": ["node_modules"]`

- Le indica al compilador que no debe procesar ni vigilar los archivos en la carpeta `node_modules`.
- Esto es importante porque `node_modules` contiene dependencias externas que no necesitas volver a compilar (además de que tiene miles de archivos y no tendría sentido analizarlos).
- Por defecto, TypeScript suele excluir `node_modules`, pero especificarlo explícitamente evita problemas.

## `include`

### `"include": ["src"]`

- Define qué archivos o carpetas quieres incluir en la compilación.
- Aquí estás diciendo que todos los archivos dentro de la carpeta `src` (y sus subcarpetas) deben ser compilados.
- Si no especificas nada, TypeScript intenta buscar archivos .ts en toda la carpeta donde se encuentra el `tsconfig.json`. Al indicar `"include": ["src"]`, te aseguras de que solo tome en cuenta tu código fuente y no otros archivos.