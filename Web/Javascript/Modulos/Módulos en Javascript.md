Los módulos permiten dividir el código en archivos independientes y reutilizables, facilitando el mantenimiento y la escalabilidad. En JavaScript, existen dos sistemas principales: **CommonJS** y **ESM (ECMAScript Modules)**.

## CommonJS
**Origen**: Surgió para resolver la falta de módulos nativos en JavaScript, adoptado principalmente por **Node.js**.

**Exportar**: `module.exports` o `exports`.

```js
// math.js
const sum = (a, b) => a + b;
module.exports = { sum };
```

**Importar**: `require()`.

```js
// app.js
const { sum } = require('./math.js');
console.log(sum(2, 3)); // 5
```

### Características
- **Carga síncrona**: Los módulos se cargan al momento de ejecutar `require()`.
- **Uso tradicional en Node.js**: Versiones antiguas lo usan por defecto.
- **Objeto `module`**: Cada módulo tiene su ámbito local.

## ESM (ECMAScript Modules)
**Origen**: Estándar nativo de JavaScript, introducido en ES6 (2015), compatible tanto en navegadores como en Node.js (desde v12+).

**Exportar**: `export` o `export default`.

```js
// math.mjs (o "type": "module" en package.json)
export const sum = (a, b) => a + b;
```

**Importar**: `import`.

```js
// app.mjs
import { sum } from './math.mjs';
console.log(sum(2, 3)); // 5
```

### Características
- **Carga asíncrona**: Mejor rendimiento en navegadores.
- **Estático**: Las importaciones se resuelven en tiempo de compilación.
- **Top-Level `await`**: Permite usar `await` fuera de funciones async.
- **Compatibilidad en Node.js**: Requiere extensión `.mjs` o `"type": "module"` en `package.json`.

## Diferencias Claves entre ambos.

| **Característica**    | **CommonJS**                    | **ESM**                 |
| --------------------- | ------------------------------- | ----------------------- |
| **Sintaxis**          | `require()` / `exports`         | `import` / `export`     |
| **Carga**             | Síncrona (Node.js)              | Asíncrona (navegadores) |
| **Ámbito**            | Objeto `module`                 | Ámbito de bloque        |
| **Node.js**           | Por defecto (sin configuración) | Requiere configuración  |
| **Top-Level `await`** | No soportado                    | Soportado               |

## Interoperabilidad

**Usar ESM en CommonJS**
```js
// En CommonJS
import('math.mjs').then(module => {
  console.log(module.sum(2, 3));
});
```

**Usar CommonJS en ESM** (Node.js):
```js
// En ESM
import { sum } from './math.cjs'; // Funciona si el archivo es CommonJS
```

## Migración y Buenas prácticas
1. **Node.js**: Configura `"type": "module"` en `package.json` para usar ESM.
2. **Navegadores**: Usa `<script type="module">` para cargar módulos ESM.
3. **Herramientas**: Usa **Babel** o **Webpack** para compatibilidad cruzada.

