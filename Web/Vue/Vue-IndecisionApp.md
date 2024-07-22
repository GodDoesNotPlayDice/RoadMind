```bash
npm create vue@latest # TS, Eslint, Devtools.
```

## Estructura del proyecto
### Estructura
```
.vscode/
node_modules/
public/
src/
├── .eslintrc.cjs
├── .gitignore
├── .prettierrc.json
├── env.d.ts
├── index.html
├── package-lock.json
├── package.json
├── README.md
├── tsconfig.app.json
├── tsconfig.json
├── tsconfig.node.json
├── tsconfig.vitest.json
├── vite.config.ts
└── vitest.config.ts

```

### Descripciones
**vitest.config.ts**: Archivo de configuración de como trabaja **vite**.
**tsconfig.node.json** : Archivo de configuración de node.
**tsconfig.json**: Archivo de configuración global de la App.
**tsconfig.app.json**: Archivo de configuración de la App.
**README.md**: Archivo que proporciona información esencial sobre un proyecto de software.
**package.json**: Todas las librerías que están en el proyecto.
**prettierrc.json**: Archivo de formatter para que todos tengamos el mismo orden.
**.gitignore**: Archivo para ignorar el git de algunos archivos.
**.eslintrc.cjs**: Reglas para hacer o seguir los componentes de Vue y seguir las buenas practicas.
**src**: El source donde se trabaja vienen todos los archivos de desarrollo.
**main.ts**: Archivo principal de la app.
**assets**: Recursos de la aplicación.
**public**: Recursos estaticos.
**.vscode**: Config sobre vscode en el proyecto.

