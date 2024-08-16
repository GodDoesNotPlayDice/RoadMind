Para instalar depende si se usa framework o vanilla.

## Framework
```bash
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

`tailwind.config.js`
```js
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    "./index.html",
    "./src/**/*.{js,ts,jsx,tsx}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

`index.css`
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

## Vanilla (CDN)

```html
  <script src="https://cdn.tailwindcss.com"></script>
```

