`vite.config.ts`: Configuración de Vite (tu herramienta de desarrollo/build): entradas, plugins, alias, ajustes de servidor, etc.
**`.env.d.ts`**  : Definiciones de tipos para variables de entorno (`import.meta.env`), para que TypeScript las reconozca sin errores.
**`tsconfig.node.json`** : Configuración de TypeScript pensada para código que corre en Node (scripts de build, configuraciones internas).
**`tsconfig.app.json`**  : Extiende o especializa `tsconfig.json` para el código de tu aplicación (excluye tests, configs de Node, etc.).
**`tsconfig.json`**  : Ajustes generales del compilador TypeScript (cómo transformar `.ts` en `.js`).
**`eslint.config.ts`**  : Reglas de ESLint para “linting” (detección de posibles errores y mantenimiento de buenas prácticas).
**`.prettierrc.json`**  : Configuración de Prettier (formateador de código) para mantener un estilo uniforme.
**`.editorconfig`**  : Normas de estilo de código comunes (tabulaciones, espacios, fin de línea) para todos los editores.
**`README.md`**  : Documentación básica del proyecto: qué es, cómo arrancarlo, etc.
**`package-lock.json`**  : Registro exacto de versiones de las dependencias instaladas, para que todos usen las mismas.
**`package.json`**  : Información del proyecto (nombre, versión, scripts) y lista de dependencias requeridas.
**`index.html`**  : Plantilla HTML principal en la que “inyectará” tu aplicación.
**`.gitignore`**  : Lista de archivos/carpetas que Git debe ignorar (no subir al repositorio)
**`.gitattributes`**  : Ajustes de Git para tratar archivos de forma especial (por ejemplo, control de finales de línea).
**`src/`**  : Todo tu código fuente en TypeScript o JavaScript (componentes, lógica, estilos).
**`public/`**  : Archivos estáticos que se sirven tal cual (imágenes, favicon, `index.html` base, etc.).
**`node_modules/`**  : Aquí se instalan todas las dependencias (librerías) que tu proyecto necesita para funcionar.
**`.vscode/`**  : Carpeta con ajustes específicos de Visual Studio Code (como atajos, configuración de depuración, etc.).