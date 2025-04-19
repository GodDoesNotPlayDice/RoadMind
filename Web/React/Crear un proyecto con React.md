Para crear un proyecto de React lo mejor es usar **vite** y usando **pnpm**

```bash
pnpm create vite@latest
```

Al crear un proyecto en React vamos a tener la siguiente estructura de archivos importantes o estructura base.
### Estructura
```
my-app/
├── node_modules/
├── public/
│   └── …  (igual que arriba)
├── src/
│   ├── App.css
│   ├── App.tsx
│   ├── index.css
│   ├── main.tsx
│   ├── logo.svg
│   ├── vite-env.d.ts
├── .gitignore
├── package.json
├── README.md
├── tsconfig.json
└── yarn.lock (o package‑lock.json)
```

Ahora lo importante esta en la carpeta **SRC** ya que ahí es donde interactuara la App, siendo `App.tsx` donde se conectara todos los módulos o [[Componentes Funcionales]] de nuestra app y `main.tsx` el vinculo con el `index.html`.